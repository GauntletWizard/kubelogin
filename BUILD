# Rules for golang support
load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

# End golang support
# Rules to build docker images
load("@io_bazel_rules_docker//go:image.bzl", "go_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_push")
# End docker support

# Rules to run Gazelle
# gazelle:prefix github.com/gauntletwizard/bazel-go
# gazelle:build_file_name BUILD,BUILD.bazel
load("@bazel_gazelle//:def.bzl", "gazelle")

gazelle(name = "gazelle")
# End Gazelle
