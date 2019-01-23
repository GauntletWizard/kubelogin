load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "github.com/gauntletwizard/bazel-go/cmd/server",
    visibility = ["//visibility:private"],
    deps = [
        "@com_github_coreos_go_oidc//:go_default_library",
        "@com_github_go_redis_redis//:go_default_library",
        "@com_github_prometheus_client_golang//prometheus:go_default_library",
        "@org_golang_x_oauth2//:go_default_library",
    ],
)

go_binary(
    name = "server",
    embed = [":go_default_library"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["main_test.go"],
    embed = [":go_default_library"],
    deps = [
        "@com_github_coreos_go_oidc//:go_default_library",
        "@com_github_smartystreets_goconvey//convey:go_default_library",
    ],
)
