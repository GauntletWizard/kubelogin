load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")
load("@io_bazel_rules_docker//go:image.bzl", "go_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_push")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "github.com/Nordstrom/kubelogin/cmd/server",
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

go_image(
    name = "dockerimage",
    embed = [":go_default_library"],
    goarch = "amd64",
    goos = "linux",
    pure = "on",
    visibility = ["//visibility:public"],
)

container_push(
    name = "push_dockerimage",
    image = "dockerimage",
    registry = "index.docker.io",
    repository = "gauntletwizard/kubelogin",
    format = "Docker",
    tag = "{BUILD_EMBED_LABEL}",
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
