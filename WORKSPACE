workspace(name = "bazel_brpc1.3_pb3.8_tf2.4")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository", "new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
BAZEL_IO_VERSION = "4.2.2"  # 2021-12-03T09:26:35Z
BAZEL_IO_SHA256 = "4c179ce66bbfff6ac5d81b8895518096e7f750866d08da2d4a574d1b8029e914"
BAZEL_SKYLIB_VERSION = "1.1.1"  # 2021-09-27T17:33:49Z
BAZEL_SKYLIB_SHA256 = "c6966ec828da198c5d9adbaa94c05e3a1c7f21bd012a0b29ba8ddbccb2c93b0d"
BAZEL_PLATFORMS_VERSION = "0.0.4"  # 2021-02-26
BAZEL_PLATFORMS_SHA256 = "079945598e4b6cc075846f7fd6a9d0857c33a7afc0de868c2ccb96405225135d"
RULES_PROTO_TAG = "4.0.0"  # 2021-09-15T14:13:21Z
RULES_PROTO_SHA256 = "66bfdf8782796239d3875d37e7de19b1d94301e8972b3cbd2446b332429b4df1"
RULES_CC_COMMIT_ID = "0913abc3be0edff60af681c0473518f51fb9eeef"  # 2021-08-12T14:14:28Z
RULES_CC_SHA256 = "04d22a8c6f0caab1466ff9ae8577dbd12a0c7d0bc468425b75de094ec68ab4f9"

http_archive(
    name = "io_bazel",
    sha256 = BAZEL_IO_SHA256,
    strip_prefix = "bazel-" + BAZEL_IO_VERSION,
    url = "https://github.com/bazelbuild/bazel/archive/" + BAZEL_IO_VERSION + ".zip",
)

http_archive(
    name = "bazel_skylib",
    sha256 = BAZEL_SKYLIB_SHA256,
    urls = [
        "https://github.com/bazelbuild/bazel-skylib/releases/download/{version}/bazel-skylib-{version}.tar.gz".format(version = BAZEL_SKYLIB_VERSION),
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/{version}/bazel-skylib-{version}.tar.gz".format(version = BAZEL_SKYLIB_VERSION),
    ],
)

http_archive(
    name = "platforms",
    sha256 = BAZEL_PLATFORMS_SHA256,
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/platforms/releases/download/{version}/platforms-{version}.tar.gz".format(version = BAZEL_PLATFORMS_VERSION),
        "https://github.com/bazelbuild/platforms/releases/download/{version}/platforms-{version}.tar.gz".format(version = BAZEL_PLATFORMS_VERSION),
    ],
)

http_archive(
    name = "rules_proto",
    sha256 = RULES_PROTO_SHA256,
    strip_prefix = "rules_proto-{version}".format(version = RULES_PROTO_TAG),
    urls = ["https://github.com/bazelbuild/rules_proto/archive/refs/tags/{version}.tar.gz".format(version = RULES_PROTO_TAG)],
)

http_archive(
    name = "rules_cc",
    sha256 = RULES_CC_SHA256,
    strip_prefix = "rules_cc-{commit_id}".format(commit_id = RULES_CC_COMMIT_ID),
    urls = [
        "https://github.com/bazelbuild/rules_cc/archive/{commit_id}.tar.gz".format(commit_id = RULES_CC_COMMIT_ID),
    ],
)

http_archive(
    name = "rules_perl",  # 2021-09-23T03:21:58Z
    sha256 = "55fbe071971772758ad669615fc9aac9b126db6ae45909f0f36de499f6201dd3",
    strip_prefix = "rules_perl-2f4f36f454375e678e81e5ca465d4d497c5c02da",
    urls = [
        "https://github.com/bazelbuild/rules_perl/archive/2f4f36f454375e678e81e5ca465d4d497c5c02da.tar.gz",
    ],
)

http_archive(
    name = "rules_foreign_cc",  # 2021-12-03T17:15:40Z
    sha256 = "1df78c7d7eed2dc21b8b325a2853c31933a81e7b780f9a59a5d078be9008b13a",
    strip_prefix = "rules_foreign_cc-0.7.0",
    url = "https://github.com/bazelbuild/rules_foreign_cc/archive/0.7.0.tar.gz",
)



http_archive(
    name = "com_google_absl",
    urls = ["https://github.com/abseil/abseil-cpp/archive/refs/tags/20240116.1.zip"],
    strip_prefix = "abseil-cpp-20240116.1"
)
git_repository(
    name = "boost",
    commit = "56ce4ba21e3610d83cfe1ddd908a67c889e86391",
    remote = "https://github.com/iceboy233/boost.git",
)

load("@boost//:boost_deps.bzl", "boost_deps")
boost_deps()


git_repository(
  name = "snappy",
  remote = "https://github.com/zhaojinzhou/snappy.git",
  branch = "v1.1.7.1"
)

bind(name = "ssl", actual = "@openssl//:ssl")
bind(name = "crypto", actual = "@openssl//:crypto")
local_repository(
    name = "org_tensorflow",
    path = "third_party/tensorflow_dynamic_2_4",
)
http_archive(
    name = "com_github_google_leveldb",  # 2021-02-23T21:51:12Z
    build_file = "//bazel/third_party/leveldb:leveldb.BUILD",
    sha256 = "9a37f8a6174f09bd622bc723b55881dc541cd50747cbd08831c2a82d620f6d76",
    strip_prefix = "leveldb-1.23",
    urls = [
        "https://github.com/google/leveldb/archive/refs/tags/1.23.tar.gz",
    ],
)

http_archive(
    name = "com_github_google_crc32c",  # 2021-10-05T19:47:30Z
    build_file = "//bazel/third_party/crc32c:crc32c.BUILD",
    sha256 = "ac07840513072b7fcebda6e821068aa04889018f24e10e46181068fb214d7e56",
    strip_prefix = "crc32c-1.1.2",
    urls = ["https://github.com/google/crc32c/archive/1.1.2.tar.gz"],
)

http_archive(
    name = "com_github_google_snappy",  # 2017-08-25
    build_file = "//bazel/third_party/snappy:snappy.BUILD",
    sha256 = "3dfa02e873ff51a11ee02b9ca391807f0c8ea0529a4924afa645fbf97163f9d4",
    strip_prefix = "snappy-1.1.7",
    urls = [
        "https://storage.googleapis.com/mirror.tensorflow.org/github.com/google/snappy/archive/1.1.7.tar.gz",
        "https://github.com/google/snappy/archive/1.1.7.tar.gz",
    ],
)

http_archive(
    name = "zlib",  # 2017-01-15T17:57:23Z
    build_file = "//bazel/third_party/zlib:zlib.BUILD",
    sha256 = "629380c90a77b964d896ed37163f5c3a34f6e6d897311f1df2a7016355c45eff",
    strip_prefix = "zlib-1.2.11",
    urls = [
        "https://github.com/madler/zlib/archive/v1.2.11.tar.gz",
    ],
)

http_archive(
    name = "com_github_madler_zlib",  # 2017-01-15T17:57:23Z
    build_file = "//bazel/third_party/zlib:zlib.BUILD",
    sha256 = "c3e5e9fdd5004dcb542feda5ee4f0ff0744628baf8ed2dd5d66f8ca1197cb1a1",
    strip_prefix = "zlib-1.2.11",
    urls = [
        "https://downloads.sourceforge.net/project/libpng/zlib/1.2.11/zlib-1.2.11.tar.gz",
        "https://zlib.net/fossils/zlib-1.2.11.tar.gz",
    ],
)

http_archive(
    name = "gflags",
    strip_prefix = "gflags-46f73f88b18aee341538c0dfc22b1710a6abedef",
    sha256 = "a8263376b409900dd46830e4e34803a170484707327854cc252fc5865275a57d",
    url = "https://github.com/gflags/gflags/archive/46f73f88b18aee341538c0dfc22b1710a6abedef.tar.gz",
)
http_archive(
    name = "com_github_gflags_gflags",
    strip_prefix = "gflags-46f73f88b18aee341538c0dfc22b1710a6abedef",
    sha256 = "a8263376b409900dd46830e4e34803a170484707327854cc252fc5865275a57d",
    url = "https://github.com/gflags/gflags/archive/46f73f88b18aee341538c0dfc22b1710a6abedef.tar.gz",
)
http_archive(
    name = "com_github_google_glog",
    build_file = "//:glog.BUILD",
    strip_prefix = "glog-a6a166db069520dbbd653c97c2e5b12e08a8bb26",
    sha256 = "367324e9ba0458b43583c7d773dc42b327e277353d03d4a9706104e2c15e8db8",
    url = "https://github.com/google/glog/archive/a6a166db069520dbbd653c97c2e5b12e08a8bb26.tar.gz"
)

http_archive(
    name = "glog",
    build_file = "//:glog.BUILD",
    strip_prefix = "glog-a6a166db069520dbbd653c97c2e5b12e08a8bb26",
    sha256 = "367324e9ba0458b43583c7d773dc42b327e277353d03d4a9706104e2c15e8db8",
    url = "https://github.com/google/glog/archive/a6a166db069520dbbd653c97c2e5b12e08a8bb26.tar.gz"
)

git_repository(
    name = "rapidjson",
    remote = "https://github.com/zhaojinzhou/rapidjson.git",
    branch = "master"
)

http_archive(
  name = "com_google_protobuf",
  strip_prefix = "protobuf-3.8.0",
  type = "zip",
  sha256 = "1e622ce4b84b88b6d2cdf1db38d1a634fe2392d74f0b7b74ff98f3a51838ee53",
  url = "https://github.com/protocolbuffers/protobuf/archive/v3.8.0.zip",
)


http_archive(
  name = "gperftools",
  strip_prefix = "gperftools-2.7_bazel", 
  type = "zip",
sha256="90a4a333ca4be45ce5345614c51cdd6cb1baf69aa3f13f623634f5fed12ad5c1",  
build_file="//:gperftools.BUILD",
  url="http://github.com/zhaojinzhou/gperftools/archive/refs/tags/v2.7_bazel.zip"
)


#new_local_repository(
#    name = "xpack",
#    # url = "https://github.com/xyz347/xpack/archive/refs/tags/v1.0.1.tar.gz",
#    # sha256 = "e1f60fdf64657c584a774271da68e6cc19c069f6853dfd9fadccea192d3e81cc",
#    path = "thirdparty/xpack-1.0.1",
#    build_file = "external/BUILD.xpack",
#    #strip_prefix = "xpack-1.0.1",
#)

git_repository(
    name = "brpc",
    remote = "https://github.com/zhaojinzhou/incubator-brpc.git",
    branch = "p_1d6510aa50075cade5ed539ee09a11a1b8d7f990"
)
