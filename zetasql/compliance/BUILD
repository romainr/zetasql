#
# Copyright 2019 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

package(default_visibility = ["//zetasql/base:zetasql_implementation"])

cc_library(
    name = "test_driver",
    testonly = 1,
    srcs = ["test_driver.cc"],
    hdrs = ["test_driver.h"],
    copts = [
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        ":test_driver_cc_proto",
        "//zetasql/base",
        "//zetasql/base:file_util",
        "//zetasql/base:path",
        "//zetasql/base:ret_check",
        "//zetasql/base:source_location",
        "//zetasql/base:status",
        "//zetasql/base:statusor",
        "//zetasql/public:language_options",
        "//zetasql/public:options_cc_proto",
        "//zetasql/public:type",
        "//zetasql/public:value",
        "//zetasql/public/functions:date_time_util",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/strings:cord",
        "@com_google_absl//absl/time",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_test(
    name = "test_driver_test",
    size = "small",
    srcs = ["test_driver_test.cc"],
    copts = [
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        ":test_driver",
        "//zetasql/public:options_cc_proto",
        "//zetasql/public:value",
        "@com_google_googletest//:gtest_main",
    ],
)

proto_library(
    name = "test_driver_proto",
    srcs = ["test_driver.proto"],
    deps = [
        "//zetasql/public:options_proto",
        "//zetasql/public:type_proto",
        "//zetasql/public:value_proto",
    ],
)

cc_proto_library(
    name = "test_driver_cc_proto",
    deps = [":test_driver_proto"],
)

java_proto_library(
    name = "test_driver_java_proto",
    deps = [":test_driver_proto"],
)

cc_library(
    name = "test_util",
    testonly = 1,
    srcs = ["test_util.cc"],
    hdrs = ["test_util.h"],
    copts = [
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        "//zetasql/base",
        "//zetasql/base:map_util",
        "//zetasql/base:status",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/flags:commandlineflag",
        "@com_google_absl//absl/flags:reflection",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/strings:str_format",
        "@com_google_protobuf//:protobuf",
    ],
)

# Not testonly because it is used by the reference implementation.
# TODO: Move to reference_impl.
cc_library(
    name = "type_helpers",
    srcs = ["type_helpers.cc"],
    hdrs = ["type_helpers.h"],
    copts = [
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        "//zetasql/base:ret_check",
        "//zetasql/base:status",
        "//zetasql/base:statusor",
        "//zetasql/public:strings",
        "//zetasql/public:type",
        "//zetasql/resolved_ast",
        "@com_google_absl//absl/strings",
    ],
)

cc_test(
    name = "type_helpers_test",
    size = "small",
    srcs = ["type_helpers_test.cc"],
    copts = [
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        ":type_helpers",
        "//zetasql/base/testing:status_matchers",
        "//zetasql/testing:test_value",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "functions_testlib",
    testonly = 1,
    srcs = [
        "functions_testlib_1.cc",
        "functions_testlib_2.cc",
        "functions_testlib_cast.cc",
        "functions_testlib_common.cc",
        "functions_testlib_format.cc",
        "functions_testlib_format_floating_point.cc",
        "functions_testlib_format_integral.cc",
        "functions_testlib_format_json.cc",
        "functions_testlib_format_nulls.cc",
        "functions_testlib_format_numeric.cc",
        "functions_testlib_format_strings.cc",
        "functions_testlib_generate_array.cc",
        "functions_testlib_json.cc",
        "functions_testlib_json_extract_array.cc",
        "functions_testlib_like.cc",
        "functions_testlib_math.cc",
        "functions_testlib_net.cc",
        "functions_testlib_regex.cc",
        "functions_testlib_string_1.cc",
        "functions_testlib_string_2.cc",
        "functions_testlib_string_3.cc",
        "functions_testlib_string_4.cc",
        "functions_testlib_string_5.cc",
        "functions_testlib_timestamp.cc",
        "functions_testlib_tojson.cc",
    ],
    hdrs = [
        "functions_testlib.h",
        "functions_testlib_common.h",
    ],
    copts = [
        "$(STACK_FRAME_UNLIMITED)",
        "-Wno-char-subscripts",
        "-Wno-return-type",
        "-Wno-sign-compare",
        "-Wno-switch",
        "-Wno-unused-but-set-parameter",
        "-Wno-unused-function",
        "-Wnonnull-compare",
    ],
    deps = [
        "//zetasql/base",
        "//zetasql/base:map_util",
        "//zetasql/base:status",
        "//zetasql/base:statusor",
        "//zetasql/base:stl_util",
        "//zetasql/common:float_margin",
        "//zetasql/common:status_payload_utils",
        "//zetasql/common/testing:testing_proto_util",
        "//zetasql/public:civil_time",
        "//zetasql/public:numeric_value",
        "//zetasql/public:options_cc_proto",
        "//zetasql/public:type",
        "//zetasql/public:type_cc_proto",
        "//zetasql/public:value",
        "//zetasql/public/functions:common_proto",
        "//zetasql/public/functions:date_time_util",
        "//zetasql/public/functions:datetime_cc_proto",
        "//zetasql/public/types",
        "//zetasql/testdata:test_schema_cc_proto",
        "//zetasql/testing:test_function",
        "//zetasql/testing:test_value",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/memory",
        "@com_google_absl//absl/status",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/strings:cord",
        "@com_google_absl//absl/strings:str_format",
        "@com_google_absl//absl/time",
        "@com_google_protobuf//:cc_wkt_protos",
        "@com_google_protobuf//:protobuf",
        "@com_googleapis_googleapis//:date_cc_proto",
        "@com_googleapis_googleapis//:latlng_cc_proto",
        "@com_googleapis_googleapis//:timeofday_cc_proto",
        "@com_googlesource_code_re2//:re2",
    ],
)
