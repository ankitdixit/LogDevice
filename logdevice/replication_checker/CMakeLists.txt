# Copyright (c) Facebook, Inc. and its affiliates.
# All rights reserved.
#
# This source code is licensed under the BSD-style license found in the
# LICENSE file in the root directory of this source tree.

add_library(replication_checker_lib
            STATIC
            "LogErrorTracker.cpp"
            "ReplicationCheckerSettings.cpp")
add_dependencies(replication_checker_lib folly common)

add_executable(ld-replication-checker main.cpp)

target_link_libraries(ld-replication-checker
  replication_checker_lib
  common
  ldclient_static
  logdevice_server
  ${LOGDEVICE_EXTERNAL_DEPS})

