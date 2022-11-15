## bRPC 作为Bazel 依赖
- 1. bRPC 内部依赖于 openssl, zlib, glog, leveldb等等, 一些开源库没有提供Bazel支持, 所以只能自行编译.
- 2. 将 ```/example/bazel_third_party_deps/external_deps/*``` 复制到你的项目根目录下.
- 3. 将 ```/example/bazel_third_party_deps/example_WORKSPACE``` 中的内容加入到你的项目 ```WORKSPACE``` or ```WORKSPACE.bazel``` 中.
- 4. bPRC 拥有 bvar, bthread, butil, brpc等等组件.

一个简单的BUILD例子:
```c++
      cc_binary(
      name = "your_binary",
      ...
      deps = [
        "@com_github_brpc_brpc//:bthread",
      ]
    )
```
  
