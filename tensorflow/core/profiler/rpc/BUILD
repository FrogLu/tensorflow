load("//tensorflow:tensorflow.bzl", "tf_cuda_library")

package(
    default_visibility = ["//visibility:public"],
    licenses = ["notice"],  # Apache 2.0
)

tf_cuda_library(
    name = "profiler_service_impl",
    srcs = ["profiler_service_impl.cc"],
    hdrs = ["profiler_service_impl.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow:grpc++",
        "//tensorflow/core:framework",
        "//tensorflow/core:grpc_services",
        "//tensorflow/core/common_runtime/eager:context",
        "//tensorflow/core/profiler:protos_all_cc",
        "//tensorflow/core/profiler/lib:profiler_eager_lib",
        "//tensorflow/core/profiler/lib:profiler_session",
    ],
    alwayslink = 1,
)

tf_cuda_library(
    name = "profiler_server",
    srcs = ["profiler_server.cc"],
    hdrs = ["profiler_server.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":profiler_service_impl",
        "//tensorflow:grpc++",
        "//tensorflow/core:framework",
        "//tensorflow/core:grpc_services",
        "//tensorflow/core/common_runtime/eager:context",
        "//tensorflow/core/profiler:protos_all_cc",
        "//tensorflow/core/profiler/lib:profiler_eager_lib",
        "//tensorflow/core/profiler/lib:profiler_session",
    ],
    alwayslink = 1,
)
