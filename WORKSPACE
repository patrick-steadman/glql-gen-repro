workspace(
    name = "gql_gen_repro",
    managed_directories = {
        "@npm": ["node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/4.5.0/rules_nodejs-4.5.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

yarn_install(
    name = "npm",
    args = [
        "--frozen-lockfile",
    ],
    data = [
    ],
    exports_directories_only = True,
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

node_repositories(package_json = ["//:package.json"])
