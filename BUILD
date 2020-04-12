load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/pseudomuto/protoc-gen-doc
# gazelle:proto disable

gazelle(name = "gazelle")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "filters.go",
        "plugin.go",
        "renderer.go",
        "resources.go",
        "template.go",
        "version.go",
    ],
    importpath = "github.com/pseudomuto/protoc-gen-doc",
    visibility = ["//visibility:public"],
    deps = [
        "//extensions:go_default_library",
        "@com_github_golang_protobuf//proto:go_default_library",
        "@com_github_masterminds_sprig//:go_default_library",
        "@com_github_gomarkdown_markdown//:go_default_library",
        "@com_github_pseudomuto_protokit//:go_default_library",
        "@io_bazel_rules_go//proto/wkt:compiler_plugin_go_proto",
        "@io_bazel_rules_go//proto/wkt:descriptor_go_proto",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "bench_test.go",
        "filters_test.go",
        "plugin_test.go",
        "renderer_test.go",
        "template_test.go",
    ],
    embed = [":go_default_library"],
    deps = [
        "//extensions:go_default_library",
        "@com_github_golang_protobuf//proto:go_default_library",
        "@com_github_pseudomuto_protokit//:go_default_library",
        "@com_github_pseudomuto_protokit//utils:go_default_library",
        "@com_github_stretchr_testify//require:go_default_library",
        "@io_bazel_rules_go//proto/wkt:compiler_plugin_go_proto",
        "@io_bazel_rules_go//proto/wkt:descriptor_go_proto",
    ],
)
