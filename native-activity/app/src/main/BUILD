load("@rules_android//rules:rules.bzl", "android_binary")
load("@rules_cc//cc:defs.bzl", "cc_library")

android_binary(
    name = "native-activity",
    manifest = "AndroidManifest.xml",
    deps = [":jni"],
)

genrule(
    name = "android_native_app_glue_h",
    srcs = ["@androidndk//:sources/android/native_app_glue/android_native_app_glue.h"],
    outs = ["android_native_app_glue.h"],
    cmd = "cp $< $@",
)

cc_library(
    name = "jni",
    srcs = [
        "cpp/main.cpp",
    ],
    hdrs = [":android_native_app_glue_h"],
    includes = ["."],
    deps = [
        "@androidndk//:native_app_glue",
    ],
)
