# Rust

> 为了安全，向编译器学习（di tou）。

- [化解神奇的闭包](./closure.md)

## Q&A 速查

- 如何加速 crates.io-index 更新速度？

执行以下命令更换镜像源

```sh
tee $HOME/.cargo/config <<-'EOF'
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
replace-with = 'ustc'
[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"
EOF
```

- 私有库 ssh 下载失败如何解决？

参考报错信息：

```
Caused by:
  failed to authenticate when downloading repository
attempted ssh-agent authentication, but none of the usernames `git` succeeded
attempted to find username/password via git's `credential.helper` support, but failed

Caused by:
  failed to acquire username/password from local configuration
```

解决办法：

```sh
ssh-add -K ~/.ssh/id_rsa
```

- Cargo build 时报`Blocking waiting for file lock on package cache`.

```
cargo build --verbose
    Blocking waiting for file lock on package cache
```

解决办法：

```
rm -r ~/.cargo/.package-cache
```

## 链接

- [PingCAP - Talent Plan](https://github.com/pingcap/talent-plan) - PingCAP 的 Rust 学习资源
- [Ferrous Teaching Material](https://github.com/ferrous-systems/teaching-material) - Rust 教学资源，非常全面
- [Book - The Rust Programming Language](https://doc.rust-lang.org/book/)
- [Rust Platform Support](https://forge.rust-lang.org/release/platform-support.html)
- [Closures: Magic Functions](https://rustyyato.github.io/rust/syntactic/sugar/2019/01/17/Closures-Magic-Functions.html)
- [Rust 编程语言](https://learnku.com/docs/rust-lang/2018) - 官方的《The Rust Programming Language》翻译
- [What is Rust and why is it so popular?](https://stackoverflow.blog/2020/01/20/what-is-rust-and-why-is-it-so-popular/)
- [Rust: A Language for the Next 40 Years - Carol Nichols](https://www.youtube.com/watch?v=A3AdN7U24iU)
- [Rust异步浅谈](https://leaxoy.github.io/2020/03/rust-async-runtime/)

### Rust 移动端跨平台

- [swapi-rust-mobile](https://github.com/xajik/rust-cross-platform-mobile)
- [Rust FFI Omnibus](http://llever.com/rust-ffi-omnibus/)
- [High performance flexbox implementation written in rust](https://github.com/vislyhq/stretch)

### 库

- [A Rust implementation of DEFLATE algorithm and related formats (ZLIB, GZIP)](https://github.com/sile/libflate)
- [FlatBuffers: Use in Rust](https://google.github.io/flatbuffers/flatbuffers_guide_use_rust.html) - Memory Efficient Serialization Library
- [Cap'n Proto for Rust](https://github.com/capnproto/capnproto-rust) - serialization/RPC system
- [maidsafe-utilities](https://github.com/maidsafe/maidsafe-utilities) - Utility functions
- [maidsafe/ffi-utils](https://github.com/maidsafe/ffi-utils)
- [getditto/safer_ffi](https://github.com/getditto/safer_ffi) - 更安全地写 FFI 代码