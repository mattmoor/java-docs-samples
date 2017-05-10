package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_appengine//appengine:appengine.bzl", "java_war")

java_war(
    name = "helloworld",
    srcs = glob(["src/main/**/*.java"]),
    deps = [
        "@servlet_api//jar:jar",
    ],
)
