F_interface_headers = files('uno_c.f90', 'uno_fortran.f90')

interface_incdirs += [include_directories('.')]

uno_F_lib = both_libraries(
    'uno',
    sources: F_interface_headers + uno_interfaces_sources,
    link_with: uno_cpp_lib,
    dependencies: uno_deps,
    include_directories: [incdirs, interface_incdirs],
)
