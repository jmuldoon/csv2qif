load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/jmuldoon/csv2qif
gazelle(
    name = "gazelle",
    args = [
        "-from_file=go.mod",
        "-to_macro=deps.bzl%go_dependencies",
        "-prune",
    ],
    command = "update-repos",
)
