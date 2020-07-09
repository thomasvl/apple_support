load("@bazel_skylib//:bzl_library.bzl", "bzl_library")

licenses(["notice"])

exports_files(["LICENSE"])

# An umbrella bzl_library for anything that needs it (like to then use stardoc),
# but odds are using the specific sub libraries go wo with the public bzl files
# are a better choice.
bzl_library(
    name = "bzl_library",
    visibility = ["//visibility:public"],
    deps = [
        "//lib:apple_support",
        "//lib:xcode_support",
        "//rules:apple_genrule",
    ],
)

# Consumed by bazel tests.
filegroup(
    name = "for_bazel_tests",
    testonly = 1,
    srcs = [
        "WORKSPACE",
        "//lib:for_bazel_tests",
        "//rules:for_bazel_tests",
        "//tools:for_bazel_tests",
    ],
    # Exposed publicly just so other rules can use this if they set up
    # integration tests that need to copy all the support files into
    # a temporary workspace for the tests.
    visibility = ["//visibility:public"],
)
