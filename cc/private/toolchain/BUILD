# Copyright 2018 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

load("@bazel_skylib//:bzl_library.bzl", "bzl_library")
load("//cc:cc_library.bzl", "cc_library")
load("//cc/toolchains:cc_flags_supplier.bzl", "cc_flags_supplier")
load("//cc/toolchains:compiler_flag.bzl", "compiler_flag")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

# It is frequently necessary to constrain platforms based on the cc compiler type.
constraint_setting(name = "cc_compiler")

constraint_value(
    name = "clang",
    constraint_setting = ":cc_compiler",
)

constraint_value(
    name = "gcc",
    constraint_setting = ":cc_compiler",
)

constraint_value(
    name = "msvc",
    constraint_setting = ":cc_compiler",
)

constraint_value(
    name = "clang-cl",
    constraint_setting = ":cc_compiler",
)

constraint_value(
    name = "mingw",
    constraint_setting = ":cc_compiler",
)

constraint_value(
    name = "msys",
    constraint_setting = ":cc_compiler",
)

cc_library(
    name = "malloc",
)

filegroup(
    name = "grep-includes",
    srcs = ["grep-includes.sh"],
)

filegroup(
    name = "empty",
    srcs = [],
)

filegroup(
    name = "bzl_srcs",
    srcs = glob(["**/*.bzl"]),
)

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
)

filegroup(
    name = "interface_library_builder",
    srcs = ["build_interface_so"],
)

filegroup(
    name = "link_dynamic_library",
    srcs = ["link_dynamic_library.sh"],
)

bzl_library(
    name = "cc_configure_bzl",
    srcs = [
        "cc_configure.bzl",
        "lib_cc_configure.bzl",
        "unix_cc_configure.bzl",
        "windows_cc_configure.bzl",
    ],
)

filegroup(
    name = "lib_cc_configure",
    srcs = ["lib_cc_configure.bzl"],
)

compiler_flag(name = "compiler")

cc_flags_supplier(name = "cc_flags")
