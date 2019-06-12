workspace(name = "gazelle_proto_issue_test_client")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

# Go rules.
http_archive(
    name = "io_bazel_rules_go",
    sha256 = "86ae934bd4c43b99893fc64be9d9fc684b81461581df7ea8fc291c816f5ee8c5",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.18.3/rules_go-0.18.3.tar.gz"],
)

# Gazelle.
# gazelle:repository_macro remote-apis-sdks-deps.bzl%remote_apis_sdks_go_deps
# TODO: switch this to an http_archive once a new Gazelle version (past 0.17) is released.
git_repository(
    name = "bazel_gazelle",
    commit = "4f524f20aff5ae9b00ecaabbf43c3e8c9804bd0b",
    remote = "https://github.com/bazelbuild/bazel-gazelle",
)

load("@io_bazel_rules_go//go:deps.bzl", "go_rules_dependencies", "go_register_toolchains")
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")
go_rules_dependencies()
go_register_toolchains()
gazelle_dependencies()

go_repository(
    name = "com_github_ifoox_gazelle_proto_issue_test",
    commit = "d47a71ade833105022fe339c5d1627be60205ecc",
    importpath = "github.com/ifoox/gazelle-proto-issue-test",
)
