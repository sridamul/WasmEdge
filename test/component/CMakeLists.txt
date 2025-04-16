# SPDX-License-Identifier: Apache-2.0
# SPDX-FileCopyrightText: 2019-2024 Second State INC

wasmedge_add_executable(componentTests
  spectest.cpp
  componentvalidatortest.cpp
)

add_test(componentTests componentTests)

file(COPY
  ${CMAKE_CURRENT_SOURCE_DIR}/componentTestData
  DESTINATION
  ${CMAKE_CURRENT_BINARY_DIR}
)

target_link_libraries(componentTests
  PRIVATE
  wasmedgeVM
  ${GTEST_BOTH_LIBRARIES}
)

target_include_directories(componentTests
  PRIVATE
  ${PROJECT_SOURCE_DIR}/include
)
