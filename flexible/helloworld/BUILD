package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_appengine//appengine:appengine.bzl", "java_war")

java_war(
    name = "helloworld",
    srcs = glob(["src/main/**/*.java"]),
    deps = [
        "@servlet_api//jar:jar",
    ],
)

load(
  "@io_bazel_rules_docker//docker:docker.bzl",
  "docker_build", "docker_push",
)

docker_build(
  name = "image",
  base = "@jetty//image:image.tar",

  # Add helloworld.war under /jetty/webapps
  directory = "/jetty/webapps",
  files = ["//:helloworld.war"],
)

docker_push(
  name = "push",
  image = ":image.tar",
  registry = "gcr.io",
  repository = "convoy-adapter/swampup",
)