#
# Build scripts to work with book examples
#
set(SRC_FILES
    smartptr.C
    smartptr_extra.C
)
#set_property(SOURCE smartptr_extra.C PROPERTY HEADER_FILE_ONLY ON)

add_executable(smartptr ${SRC_FILES})
target_link_libraries(smartptr PRIVATE benchmark::benchmark)
add_test(NAME smartptr COMMAND $<TARGET_FILE:smartptr>)
