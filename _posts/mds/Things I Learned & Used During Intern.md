# Things I Learned & Used During Intern

## Books

https://rust-exercises.com/telemetry/
https://doc.rust-lang.org/nomicon/races.html

## Knowledge

- Kafka basics

The whole projects runtime is copied from kube-rs.
The runtime of databus is copied from Vector.

- Useful Websites

    - https://samwho.dev/bloom-filters/
    - https://tokio.rs/tokio/tutorial/async
    - https://sre.google/sre-book/introduction/
    - https://rustwasm.github.io/docs/book/game-of-life/implementing.html
    - https://skyzh.github.io/mini-lsm/week2-overview.html
    - https://dioxuslabs.com/learn/0.6/guides/fullstack/server_functions#
    - https://javascript.info/object
    - https://mycompiler.io/

## Tools

- axum
- SeaORM
- rdkafka
- snafu
- clap
- redis
- tonic?
- wasm-bindgen
- 

## Useful Tricks

- oh-my-zsh
- If bash by default and cannot be changed, add `exec /bin/zsh` into `.bash_profile`. Note that the env for zsh is independent from bash.
- git-completion.bash + git-completion.zsh

To copy from shell:

On macOS, use pbcopy:
$ <command> | pbcopy

On Windows, use clip:
$ <command> | clip

On Linux with Wayland (most distributions), use wl-copy:
$ <command> | wl-copy

On Linux with X11 (typically older distributions), use xclip:
$ <command> | xclip

## Small programs

### Mini Arc in C++

```C++
#include <atomic>
#include <iostream>
#include <memory>

template<typename T>
class Block {
private:
    std::atomic<size_t> ref_cnt;
    T* data;

public:
    explicit Block(T* data) : ref_cnt(1), data(data) {}

    size_t get_ref_cnt() const { return ref_cnt.load(); }

    void add_ref() {
        printf("add one\n");
        ref_cnt.fetch_add(1);
    }

    void remove_ref() {
        if (ref_cnt.fetch_sub(1) == 1) {
            printf("drop one\n");
            delete data;
        }
    }

    T* get() const {
        return data;
    }
};

template<typename T>
class Arc {
private:
    Block<T>* block;

public:
    explicit Arc(T&& data) {
        block = new Block<T>(&data);
    }

    Arc(Arc&& that) noexcept {
        block = that.block;
        block->add_ref();
        that.block = nullptr;
    }

    Arc(const Arc& that) {
        block = that.block;
        block->add_ref();
    }

    ~Arc() {
        if (block != nullptr) {
            block->remove_ref();
            if (block->get_ref_cnt() == 0) {
                delete block;
            }
        }
    }

   void operator=(const Arc& that) = delete;

    T* get() {
        return this->block->get();
    }
};

auto get_ref(Arc<int>&& ori) -> Arc<int> {
    return ori;
}

int main() {
    auto data = new int(2);
    Arc<int> arc(std::move(*data));
    Arc<int> ref = get_ref(std::move(arc));
    std::cout << *ref.get() << std::endl;
    return 0;
}
```
