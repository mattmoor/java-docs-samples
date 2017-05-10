package(default_visibility = ["//visibility:private"])

load(
  "@io_bazel_rules_docker//docker:docker.bzl",
  "docker_build", "docker_push",
)

docker_build(
  name = "image",
  base = "@jetty//image:image.tar",
  directory = "/jetty/webapps",
  files = ["//:helloworld.war"],
  workdir = "/jetty",
)

docker_push(
  name = "push",
  image = ":image.tar",
  registry = "gcr.io",
  repository = "convoy-adapter/bazel-examples",
  tag = "helloworld-bazel",
)