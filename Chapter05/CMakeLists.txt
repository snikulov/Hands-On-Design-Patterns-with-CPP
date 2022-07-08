#
# Build scripts to work with book examples
#
set(SRC_FILES
    scoped_ptr1_bm.C
)
set(TEST_FILES
    memory1.C
    mutex1.C
    scoped_ptr1.C
)


foreach(_file ${SRC_FILES})
    get_filename_component(_exe_name ${_file} NAME_WE)
    add_executable(${_exe_name} ${_file})
    target_link_libraries(${_exe_name} PRIVATE benchmark::benchmark)
    add_test(NAME ${_exe_name} COMMAND $<TARGET_FILE:${_exe_name}>)
endforeach()

foreach(_tfile ${TEST_FILES})
    get_filename_component(_texe_name ${_tfile} NAME_WE)
    add_executable(${_texe_name} ${_tfile})
    target_link_libraries(${_texe_name} PRIVATE GTest::gtest GTest::gtest_main)
    add_test(NAME ${_texe_name} COMMAND $<TARGET_FILE:${_texe_name}>)
endforeach()
