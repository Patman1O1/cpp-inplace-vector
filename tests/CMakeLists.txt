# ── Google Test ──────────────────────────────────────────────────────────────
include(GoogleTest)
enable_testing()

# ───────────────────────────────────────────────────────────────────────────── 
# Target: cpp_inplace_vector_test
# Alias: cpp_inplace_vector::cpp_inplace_vector_test
# Type: Executable
# Dependencies: GTest::gtest_main,
#               GTest::gmock_main,
#               cpp_inplace_vector::cpp_inplace_vector_headers
# ─────────────────────────────────────────────────────────────────────────────
# Target definition
add_executable(cpp_inplace_vector_test)

# Target alias
add_executable(cpp_inplace_vector::cpp_inplace_vector_test
    ALIAS cpp_inplace_vector_test
)

# Target sources
target_sources(cpp_inplace_vector_test
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/cpp_inplace_vector_test.cpp
)

# Target dependencies
target_link_libraries(cpp_inplace_vector_test
    PRIVATE
        cpp_inplace_vector::cpp_inplace_vector_headers
        GTest::gtest_main
        GTest::gmock_main
)

# Test discovery
gtest_discover_tests(cpp_inplace_vector_test)
