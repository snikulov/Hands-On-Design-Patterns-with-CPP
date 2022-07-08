#
# Build scripts to work with book examples
#

set(SRC_FILES
    fast_sort1.C
    fast_sort2.C
    fast_sort3.C
    fast_sort4.C
    incomplete_template1.C
    incomplete_template_ctor.C
    is_class1.C
    is_class2.C
    is_class3.C
    is_valid1.C
    is_valid1a.C
    is_valid2.C
    is_valid2a.C
    is_valid3.C
    is_valid4.C
    multiply1.C
    multiply2.C
    multiply3.C
    multiply4.C
    multiply5.C
    overload1.C
    overload1a.C
    overload1b.C
    overload2.C
    overload3.C
    overload4.C
    overload6.C
    sfinae1.C
    sfinae1a.C
    sfinae2.C
    sfinae3.C
    sfinae4.C
)
set(NON_CMPL_SRC
    incomplete_class.C
    incomplete_ctor.C
    incomplete_template2.C
    no_sfinae1.C
    overload5.C
)
set_property(SOURCE ${NON_CMPL_SRC} PROPERTY HEADER_FILE_ONLY ON)

foreach(_file ${SRC_FILES})
    get_filename_component(_exe_name ${_file} NAME_WE)
    add_executable(${_exe_name} ${_file} ${NON_CMPL_SRC})
endforeach()
