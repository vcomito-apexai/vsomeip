cc_binary(
    name = "libvsomeip3.so",
    linkopts = ["-Wl,--no-undefined"],
    linkshared = True,
    linkstatic = True,
    tags = ["same-ros-pkg-as: vsomeip3"],
    deps = [
        "//implementation",
    ],
)

cc_binary(
    name = "libvsomeip3-cfg.so.3",
    linkopts = ["-Wl,--no-undefined"],
    linkshared = True,
    linkstatic = True,
    tags = ["same-ros-pkg-as: vsomeip3"],
    visibility = ["//visibility:public"],
    deps = [
        "//implementation:configuration",
    ],
)

cc_binary(
    name = "libvsomeip3-sd.so.3",
    linkopts = ["-Wl,--no-undefined"],
    linkshared = True,
    linkstatic = True,
    tags = ["same-ros-pkg-as: vsomeip3"],
    visibility = ["//visibility:public"],
    deps = [
        "//implementation:service_discovery",
    ],
)

cc_import(
    name = "vsomeip3_import",
    shared_library = ":libvsomeip3.so",
    tags = ["same-ros-pkg-as: vsomeip3"],
    deps = ["//interface"],
)

# interface library, use this target to depend on vsomeip
cc_library(
    name = "vsomeip3",
    data = [
        "libvsomeip3-cfg.so.3",
        "libvsomeip3-sd.so.3",
    ],
    linkstatic = True,  # no object files
    visibility = ["//visibility:public"],
    deps = [":vsomeip3_import"],
)
