#
# Build scripts to work with book examples
#
set(SRC_FILES
    smartptr.C
    smartptr_extra.C
)
set_source_files_properties(SRC_FILES PROPERTIES HEADER_FILE smartptr.C)

add_executable(smartptr ${SRC_FILES})
target_link_libraries(smartptr PRIVATE benchmark::benchmark)
add_test(NAME smartptr COMMAND $<TARGET_FILE:smartptr>)
