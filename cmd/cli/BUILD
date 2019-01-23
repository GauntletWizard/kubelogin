load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "github.com/gauntletwizard/bazel-go/cmd/cli",
    visibility = ["//visibility:private"],
    deps = [
        "@com_github_pkg_errors//:go_default_library",
        "@in_gopkg_yaml_v2//:go_default_library",
    ],
)

go_binary(
    name = "cli",
    embed = [":go_default_library"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["main_test.go"],
    embed = [":go_default_library"],
    deps = [
        "@com_github_smartystreets_goconvey//convey:go_default_library",
        "@in_gopkg_yaml_v2//:go_default_library",
    ],
)
