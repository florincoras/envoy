load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_extension_package",
)

licenses(["notice"])  # Apache 2

# VPP Comms Lib (VCL) adaptor.

envoy_extension_package()

envoy_cc_library(
    name = "vcl_interface_lib",
    srcs = [
        "vcl_event.cc",
        "vcl_interface.cc",
        "vcl_io_handle.cc",
        "vppr/lib/libvppcom.so.21.06",
    ],
    hdrs = [
        "vcl_event.h",
        "vcl_interface.h",
        "vcl_io_handle.h",
        "vppr/include/vcl/vppcom.h",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//include/envoy/event:dispatcher_interface",
        "//include/envoy/network:socket_interface",
        "//source/common/common:logger_lib",
        "//source/common/event:dispatcher_includes",
        "//source/common/event:dispatcher_lib",
        "//source/common/event:libevent_scheduler_lib",
        "//source/common/network:address_lib",
        "//source/common/network:io_socket_error_lib",
        "//source/common/network:socket_interface_lib",
        "//source/common/network:socket_lib",
        "@envoy_api//envoy/extensions/network/socket_interface/v3:pkg_cc_proto",
    ],
)
