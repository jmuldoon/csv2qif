load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/jmuldoon/csv2qif
gazelle(name = "gazelle")

gazelle(
    name = "gazelle-update-repos",
    args = [
        "-from_file=go.mod",
        "-to_macro=deps.bzl%go_dependencies",
        "-prune",
        "-build_file_proto_mode=disable_global",
    ],
    command = "update-repos",
)

load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "csv2qif_lib",
    srcs = ["main.go"],
    importpath = "github.com/jmuldoon/csv2qif",
    visibility = ["//visibility:private"],
    deps = ["//cmd"],
)

go_binary(
    name = "csv2qif",
    embed = [":csv2qif_lib"],
    visibility = ["//visibility:public"],
)
