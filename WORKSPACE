load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

## Docker rules
# https://github.com/bazelbuild/rules_docker

git_repository(
    name = "io_bazel_rules_docker",
    remote = "https://github.com/bazelbuild/rules_docker.git",
    # Head as of 12/15/2018
    commit = "f6664b6b5c7f4fac031883a7ec9fa6b8bab0ab98",
)

load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_pull",
    container_repositories = "repositories",
)

## Go rules
# https://github.com/bazelbuild/rules_go#generating-build-files

http_archive(
    name = "io_bazel_rules_go",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.16.5/rules_go-0.16.5.tar.gz"],
    sha256 = "7be7dc01f1e0afdba6c8eb2b43d2fa01c743be1b9273ab1eaf6c233df078d705",
)

load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains")

go_rules_dependencies()

go_register_toolchains()

load(
    "@io_bazel_rules_docker//go:image.bzl",
    _go_image_repos = "repositories",
)

_go_image_repos()

# Gazelle
git_repository(
    name = "bazel_gazelle",
    remote = "https://github.com/GauntletWizard/bazel-gazelle.git",
    commit = "4d4ba26e46aa2b3830d64608743563ffd5ec2567",
)

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")

gazelle_dependencies()

## Below here are the Gazelle managed deps:

go_repository(
    name = "org_golang_google_grpc",
    commit = "14de8b69c256b7852a584af9f3a398ff6f8d2697",
    importpath = "google.golang.org/grpc",
)

go_repository(
    name = "com_github_beorn7_perks",
    commit = "4c0e84591b9aa9e6dcfdf3e020114cd81f89d5f9",
    importpath = "github.com/beorn7/perks",
)

go_repository(
    name = "com_github_coreos_go_oidc",
    commit = "d68c0e2fef598f5bbf15edd34905f4bf551a54ec",
    importpath = "github.com/coreos/go-oidc",
)

go_repository(
    name = "com_github_go_redis_redis",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis",
)

go_repository(
    name = "com_github_go_redis_redis_internal",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis/internal",
)

go_repository(
    name = "com_github_go_redis_redis_internal_consistenthash",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis/internal/consistenthash",
)

go_repository(
    name = "com_github_go_redis_redis_internal_hashtag",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis/internal/hashtag",
)

go_repository(
    name = "com_github_go_redis_redis_internal_pool",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis/internal/pool",
)

go_repository(
    name = "com_github_go_redis_redis_internal_proto",
    commit = "7a034e1609674d5eb847c3885e5058c54e79a1df",
    importpath = "github.com/go-redis/redis/internal/proto",
)

go_repository(
    name = "com_github_golang_protobuf_proto",
    commit = "748d386b5c1ea99658fd69fe9f03991ce86a90c1",
    importpath = "github.com/golang/protobuf/proto",
)

go_repository(
    name = "com_github_gopherjs_gopherjs_js",
    commit = "dc374d32704510cb387457180ca9d5193978b555",
    importpath = "github.com/gopherjs/gopherjs/js",
)

go_repository(
    name = "com_github_jtolds_gls",
    commit = "77f18212c9c7edc9bd6a33d383a7b545ce62f064",
    importpath = "github.com/jtolds/gls",
)

go_repository(
    name = "com_github_matttproud_golang_protobuf_extensions",
    commit = "c12348ce28de40eed0136aa2b644d0ee0650e56c",
    importpath = "github.com/matttproud/golang_protobuf_extensions",
)

go_repository(
    name = "com_github_pkg_errors",
    commit = "c605e284fe17294bda444b34710735b29d1a9d90",
    importpath = "github.com/pkg/errors",
)

go_repository(
    name = "com_github_pquerna_cachecontrol",
    commit = "5475d973ea70916980bee28c2b674f3dc3eaed0a",
    importpath = "github.com/pquerna/cachecontrol",
)

go_repository(
    name = "com_github_pquerna_cachecontrol",
    commit = "5475d973ea70916980bee28c2b674f3dc3eaed0a",
    importpath = "github.com/pquerna/cachecontrol",
)

go_repository(
    name = "com_github_prometheus_client_model",
    commit = "6f3806018612930941127f2a7c6c453ba2c527d2",
    importpath = "github.com/prometheus/client_model",
)

go_repository(
    name = "com_github_prometheus_common",
    commit = "61f87aac8082fa8c3c5655c7608d7478d46ac2ad",
    importpath = "github.com/prometheus/common",
)

go_repository(
    name = "com_github_prometheus_procfs",
    commit = "e645f4e5aaa8506fc71d6edbc5c4ff02c04c46f2",
    importpath = "github.com/prometheus/procfs",
)

go_repository(
    name = "com_github_prometheus_procfs",
    commit = "e645f4e5aaa8506fc71d6edbc5c4ff02c04c46f2",
    importpath = "github.com/prometheus/procfs",
)

go_repository(
    name = "com_github_smartystreets_assertions",
    commit = "4ea54c1f28ad3ae597e76607dea3871fa177e263",
    importpath = "github.com/smartystreets/assertions",
)

go_repository(
    name = "in_gopkg_square_go_jose_v2",
    commit = "b25e6cab129e4a54675b42ea49d38e9c33ade9e6",
    importpath = "gopkg.in/square/go-jose.v2",
)

go_repository(
    name = "in_gopkg_yaml_v2",
    commit = "cd8b52f8269e0feb286dfeef29f8fe4d5b397e0b",
    importpath = "gopkg.in/yaml.v2",
)

go_repository(
    name = "org_golang_x_net_context",
    commit = "5f8847ae0d0e90b6a9dc8148e7ad616874625171",
    importpath = "golang.org/x/net/context",
)

go_repository(
    name = "org_golang_x_oauth2",
    commit = "cce311a261e6fcf29de72ca96827bdb0b7d9c9e6",
    importpath = "golang.org/x/oauth2",
)

go_repository(
    name = "com_github_smartystreets_goconvey",
    commit = "044398e4856c3a83fb98f9de0a8ed1c6495e2843",
    importpath = "github.com/smartystreets/goconvey",
)

go_repository(
    name = "com_github_prometheus_client_golang",
    commit = "26e258bb9c9a94c26d4a46ff302ec7e855b82e10",
    importpath = "github.com/prometheus/client_golang",
)
