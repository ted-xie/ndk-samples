load("@rules_android//rules:rules.bzl", "android_binary")
load("@rules_cc//cc:defs.bzl", "cc_library")

android_binary(
    name = "native-activity",
    deps = [":jni"],
    manifest = "AndroidManifest.xml",
)

cc_library(
    name = "jni",
    srcs = [
        "cpp/main.cpp", 
    ],
    deps = [
        "@androidndk//:native_app_glue",
    ],
    copts = ["-Iexternal/rules_android_ndk~~android_ndk_repository_extension~androidndk/sources/android/native_app_glue"],
)
