
licenses(["notice"])

load("@tsl//tsl:tsl.bzl", _if_windows = "if_windows", pybind_extension = "tsl_pybind_extension_opensource")

package(
    default_applicable_licenses = [],
    default_visibility = ["//:__subpackages__"],
)

cc_library(
    name = "clang_compile",
    srcs = ["clang_compile.cc"],
    hdrs = ["clang_compile.h"],
    deps = [
        "@llvm-project//clang:ast",
        "@llvm-project//clang:basic",
        "@llvm-project//clang:driver",
        "@llvm-project//clang:frontend",
        "@llvm-project//clang:frontend_tool",
        "@llvm-project//clang:lex",
        "@llvm-project//clang:serialization",
        "@llvm-project//llvm:Support",
        "@llvm-project//llvm:Core",
        "@llvm-project//llvm:IRReader",
    ],
)

pybind_extension(
    name = "enzyme_call",
    srcs = ["enzyme_call.cc"],
    deps = [
        "@pybind11",
        "@llvm-project//llvm:Support",
        ":clang_compile",
    ],
)

pybind_extension(
    name = "pyllvm",
    srcs = ["pyllvm.cc"],
    deps = [
        "@pybind11",
        "@llvm-project//llvm:Support",
        ":clang_compile",
    ],
)
