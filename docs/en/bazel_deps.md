## bRPC as an external dependency
- 1. bRPC internally dependent on openssl, zlib, glog, leveldb so so, some opensource code don't provide the bazel support. So you must compile it youself.
- 2. copy the ```/example/bazel_third_party_deps/external_deps/*``` to your project root path.
- 3. add the ```/example/bazel_third_party_deps/external_deps/example_WORSKAPCE``` to your project ```WORKSAPCE``` or ```WORKSPACE.bazel```.
- 4. bRPC have bvar, bthread, butil, brpc etc. components.

a simple BUILD example like
```c++
      cc_binary(
      name = "your_binary",
      ...
      deps = [
        "@com_github_brpc_brpc//:bthread",
      ]
    )
```