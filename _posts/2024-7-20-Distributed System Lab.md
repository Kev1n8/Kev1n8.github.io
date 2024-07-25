---
title: "Distributed System Lab"
published: true
---

# Distributed System Labs

Some drafts and notes.

## #1 MapReduce

### test_mr.sh

`mrcoordinator .{{site.baseurl}}/pg*txt`

then multiple workers

`mrworker .{{site.baseurl}}/.{{site.baseurl}}/mrapps/app.so`

**Workflow**:

master awake, prepare rpc and splits. workers awake, prepare map/reduce functions and start asking for task.

1. master get M map tasks and R reduce tasks ready. picking up workers to assign
2. map workers read the splits and save the intermediate files, tell the master about the R locations(which files)
3. master receive task done msg, master picks workers to do reduce task, telling them the location of the R they are going to deal with.
4. reduce workers use rpc to read target R files from different map workers. once all read, sort them all by inter-key. reduce workers then iterate over the sorted data and do reduce func. the ouput of the func is appended to a final output file of this R partition. done, call master is done
5. once all done, master

#### Conclusion

So I suppose that this is not that hard since it didn't take much time for me to accomplish the task. To be honest, the reason I'd been stuck for a little while when `bash test-mr.sh` is because the path of the file is incorrect (changed it to absolute path later ). 

## #2 Key/Value Server

To implement an in-memory server and clients. It's pretty easy that there's really no much to talk about.

**Techniques Used**

1. Still, using **RPC** to call remote functions
2. Using *unique Ids* to represent each of the clients and each request. 

**2 Things blocked me for a while**

1. A silly mistake - the fact is that `Call()` is executed only once, and then there's a terrible infinite loop

    ```Go
    for ok := ck.Call("Server.Put", &args, &reply); !ok
    ```

2. Using *Unique Ids* to represent `values` instead of Reqs - bad things would happen when other clients change the record, hence causing duplicate put/append

#### Conclusion

The lab is marked **Easy**, which is true just that I am supposed to finish it in real quick.

## #3 Raft

### Election

I've drawn a figure listing out the summary of rules, check out:

![state_transfer]({{site.baseurl}}/images/election_state.png){:height="400px" width="auto"}

Also, some variables and details as:

![election_variables_rules]({{site.baseurl}}/images/election_variable&rules.png){:height="400px" width="auto"}

### Log

The rule of log replication can be interpreted as the following graphs:

![log_replication_basic]({{site.baseurl}}/images/log_replication_basic.png){:height="400px" width="auto"}

Demonstrating an unreliable test that I'd debugged for a while and Tips:

![log_replication_atest]({{site.baseurl}}/images/log_replication_atest.png){:height="400px" width="auto"}

In order to back up faster, I also implement the following technique:

![log_replication_quick_backup]({{site.baseurl}}/images/log_replication_quick_backup.png){:height="400px" width="auto"}

By sending `XTerm`, `XIndex`, and `Len` back to the leader, the leader can then quickly decide what `nextIndex[target]` should be set and get rid of meaningless retries.

### Persistence

![persistence_summary]({{site.baseurl}}/images/persistence_summary.png){:height="400px" width="auto"}

### Log Compaction

![log_compaction_procedure]({{site.baseurl}}/images/log_compaction_procedure.png){:height="400px" width="auto"}

![log_compaction_points]({{site.baseurl}}/images/log_compaction_points.png){:height="400px" width="auto"}

## #4 Fault-Tolerant K/V Service

Note: All of the fields in RPC args should be initialized, otherwise the RPC will fail.(on returning(never return))

![lab4]({{site.baseurl}}/images/lab4.png){:height="400px" width="auto"}
