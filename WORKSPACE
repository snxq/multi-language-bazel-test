# WORKSPACE
# load http_archive
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# get rules_go
http_archive(
    name = "io_bazel_rules_go",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.19.4/rules_go-0.19.4.tar.gz"],
    sha256 = "ae8c36ff6e565f674c7a3692d6a9ea1096e4c1ade497272c2108a810fb39acd2",
)

# get gazelle
http_archive(
    name = "bazel_gazelle",
    urls = ["https://github.com/bazelbuild/bazel-gazelle/releases/download/0.18.2/bazel-gazelle-0.18.2.tar.gz"],
    sha256 = "7fc87f4170011201b1690326e8c16c5d802836e3a0d617d8f75c3af2b23180c4",
)

# load go_rules
load("@io_bazel_rules_go//go:deps.bzl", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()
go_register_toolchains()

# load gazelle
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")
gazelle_dependencies()

# load git_repository
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

# get rules_python
git_repository(
    name = "io_bazel_rules_python",
    remote = "https://github.com/bazelbuild/rules_python.git",
    commit = "23790d0e6acb4f16ab2b5158688e7feeb3e89eb6",
)

# Only needed for PIP support:
# load("@io_bazel_rules_python//python:pip.bzl", "pip_repositories")

# pip_repositories()


# get rust rules
http_archive(
    name = "io_bazel_rules_rust",
    sha256 = "615639cfd5459fec4b8a5751112be808ab25ba647c4c1953d29bb554ef865da7",
    strip_prefix = "rules_rust-0.0.6",
    urls = [
        "http://bazel-mirror.storage.googleapis.com/github.com/bazelbuild/rules_rust/archive/0.0.6.tar.gz",
        "https://github.com/bazelbuild/rules_rust/archive/0.0.6.tar.gz",
    ],
)

# load rust rules
load("@io_bazel_rules_rust//rust:repositories.bzl", "rust_repositories")

rust_repositories()