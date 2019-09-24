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
    name = "rules_python",
    remote = "https://github.com/bazelbuild/rules_python.git",
    # NOT VALID!  Replace this with a Git commit SHA.
    commit = "54d1cb35cd54318d59bf38e52df3e628c07d4bbc",
)

# This call should always be present.
load("@rules_python//python:repositories.bzl", "py_repositories")
py_repositories()

# This one is only needed if you're using the packaging rules.
load("@rules_python//python:pip.bzl", "pip_repositories")
pip_repositories()


# get rust rules
http_archive(
    name = "io_bazel_rules_rust",
    sha256 = "d6cd71c711ccbbaa5772818f2607a9da5f4c0d29f37cf69d3c0270143f047f58",
    strip_prefix = "rules_rust-f727669b8ac3c9d237ed9bc7833b8e1eeec90506",
    urls = [
        "https://github.com/bazelbuild/rules_rust/archive/f727669b8ac3c9d237ed9bc7833b8e1eeec90506.zip"
    ],
)

load("@io_bazel_rules_rust//rust:repositories.bzl", "rust_repositories")
rust_repositories()

load("@io_bazel_rules_rust//:workspace.bzl", "bazel_version")
bazel_version(name = "bazel_version")
