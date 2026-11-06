# interface_incdirs += [include_directories('.')]
# interface_incdirs = [include_directories('.')]
interface_incdirs = []

C_interface_headers = files('Uno_C_API.h', 'uno_int.h')

uno_C_interfaces_sources = files('Uno_C_API.cpp', 'Uno_C_API.h', 'uno_int.h')

# uno_C_lib = both_libraries(
#     'uno',
#     sources: uno_C_interfaces_sources + uno_interfaces_sources,
#     link_with: uno_cpp_lib,
#     dependencies: uno_deps,
#     include_directories: [incdirs, interface_incdirs],
# )

# install_headers(C_interface_headers)
# uno_C_lib = library(
#     'uno',
#     sources: uno_C_interfaces_sources + uno_interfaces_sources, # uno_sources + uno_interfaces_sources,
#     dependencies: uno_deps,
#     link_with: uno_cpp_lib,
#     include_directories: [incdirs, interface_incdirs],
#     install: true,
# )
if build_shared and build_static
    uno_C_lib = both_libraries(
        'uno',
        sources: uno_C_interfaces_sources + uno_interfaces_sources + uno_sources + uno_headers,
        dependencies: uno_deps,
        # link_with: uno_cpp_lib,
        cpp_args: comp_args,
        include_directories: [incdirs, interface_incdirs],
        install: true,
    )
elif build_shared
    uno_C_lib = shared_library(
        'uno',
        sources: uno_C_interfaces_sources + uno_interfaces_sources + uno_sources + uno_headers,
        dependencies: uno_deps,
        # link_with: uno_cpp_lib,
        cpp_args: comp_args,
        include_directories: [incdirs, interface_incdirs],
        install: true,
    )
elif build_static
    uno_C_lib = static_library(
        'uno',
        sources: uno_C_interfaces_sources + uno_interfaces_sources + uno_sources + uno_headers,
        dependencies: uno_deps,
        # link_with: uno_cpp_lib,
        include_directories: [incdirs, interface_incdirs],
        cpp_args: comp_args,
        c_args: comp_args,
        install: true,
    )
endif

uno_C_lib_dep = declare_dependency(
  link_with: uno_C_lib,
  compile_args: comp_args
)

install_headers(C_interface_headers, install_dir: 'include/uno')

subdir('example')
