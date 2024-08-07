# Car related tasks.
# buildifier: disable=same-origin-load
# Placeholder: load py_binary
# Placeholder: load py_library
# Placeholder: load py_test

package(default_visibility = [
    "//visibility:public",
])

licenses(["notice"])

py_test(
    name = "waymo_ap_metric_test",
    srcs = ["waymo_ap_metric_test.py"],
    # TODO(b/208324211): Skip until waymo-open-dataset-2-7-0 is released.
    tags = ["manual"],
    deps = [
        ":waymo_ap_metric",
        ":waymo_metadata",
        #internal proto upb dep
        "//lingvo:compat",
        "//lingvo/core:py_utils",
        "//lingvo/core:test_utils",
        # Implicit numpy dependency.
        # Implicit Waymo Open Dataset label dependency.
        # Implicit Waymo Open Dataset metrics_proto dependency.
    ],
)

py_test(
    name = "waymo_open_input_generator_test",
    srcs = ["waymo_open_input_generator_test.py"],
    deps = [
        ":waymo_open_input_generator",
        #internal proto upb dep
        "//lingvo:compat",
        "//lingvo/core:py_utils",
        "//lingvo/core:test_utils",
        # Implicit numpy dependency.
    ],
)

py_library(
    name = "waymo_ap_metric",
    srcs = [
        "waymo_ap_metric.py",
    ],
    deps = [
        "//lingvo:compat",
        "//lingvo/core:py_utils",
        "//lingvo/tasks/car:ap_metric",
        # Implicit numpy dependency.
        # Implicit Waymo Open Dataset label dependency.
        # Implicit Waymo Open Dataset detection metrics dependency.
        # Implicit Waymo Open Dataset py_metrics dependency.
        # Implicit Waymo Open Dataset config_util_py dependency.
        # Implicit Waymo Open Dataset breakdown_proto dependency.
        # Implicit Waymo Open Dataset metrics_proto dependency.
    ],
)

py_library(
    name = "waymo_decoder",
    srcs = ["waymo_decoder.py"],
    deps = [
        ":waymo_ap_metric",
        ":waymo_metadata",
        "//lingvo:compat",
        "//lingvo/core:metrics",
        "//lingvo/core:py_utils",
        "//lingvo/tasks/car:base_decoder",
        "//lingvo/tasks/car:detection_3d_metrics",
        "//lingvo/tasks/car:transform_util",
        # Implicit numpy dependency.
    ],
)

py_library(
    name = "waymo_metadata",
    srcs = [
        "waymo_metadata.py",
    ],
    deps = [
        "//lingvo/tasks/car:evaluation_metadata",
    ],
)

py_library(
    name = "waymo_open_input_generator",
    srcs = ["waymo_open_input_generator.py"],
    deps = [
        "//lingvo:compat",
        "//lingvo/core:datasource",
        "//lingvo/core:hyperparams",
        "//lingvo/core:py_utils",
        "//lingvo/tasks/car:input_extractor",
        "//lingvo/tasks/car:input_preprocessors",
        # Implicit numpy dependency.
        # Implicit Waymo Open Dataset camera model projection (kernel) dependency.
        # Implicit Waymo Open Dataset camera model projection dependency.
    ],
)

py_library(
    name = "export_to_submission_format_lib",
    srcs = ["export_to_submission_format.py"],
    deps = [
        # Implicit absl.flags dependency.
        "//lingvo:compat",
        "//lingvo/core/ops:record_py_pb2",
        # Implicit Waymo Open Dataset metrics_proto dependency.
    ],
)

py_binary(
    name = "export_to_submission_format",
    srcs = ["export_to_submission_format.py"],
    deps = [":export_to_submission_format_lib"],
)
