#
# Build scripts to work with book examples
#

set(SRC_FILES
    list_swap.C
    member_swap.C
    nonmember_swap_friend.C
    nonmember_swap_friend_forward.C
    nonmember_swap_func.C
    nonmember_swap_none.C
    nonmember_swap_std.C
    nonmember_swap_std_only.C
    std_swap_copyable.C
    std_swap_movable.C
# Will not compile cause of deleted copy/move constructors
#    std_swap_noncopyable.C
#    std_swap_nonmovable.C
    swap_rollback.C
    vector_empty.C
    vector_swap.C
)

foreach(_file ${SRC_FILES})
    get_filename_component(_exe_name ${_file} NAME_WE)
    add_executable(${_exe_name} ${_file})
endforeach()
