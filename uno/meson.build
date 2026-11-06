incdirs += [include_directories('.')]

uno_headers = []
uno_sources = []

subdir('linear_algebra')
subdir('ingredients')
subdir('model')
subdir('optimization')
subdir('options')
subdir('symbolic')
subdir('tools')

uno_headers += [files('Uno.hpp')]
uno_sources += [files('Uno.cpp')]
# uno_cpp_lib = library(
#     'unoCpp',
#     sources: uno_sources + uno_headers,
#     dependencies: uno_deps,
#     install: false,
#     include_directories: incdirs,
# )



# if build_shared and build_static
#     uno_cpp_lib = both_libraries(
#         'unoCpp',
#         sources: uno_sources + uno_headers,
#         dependencies: uno_deps,
#         install: false,
#         include_directories: incdirs,
#     )
# elif build_shared
#     uno_cpp_lib = shared_library(
#         'unoCpp',
#         sources: uno_sources + uno_headers,
#         dependencies: uno_deps,
#         install: false,
#         include_directories: incdirs,
#     )
# elif build_static
#     uno_cpp_lib = static_library(
#         'unoCpp',
#         include_directories: incdirs,
#         sources: uno_sources + uno_headers,
#         dependencies: uno_deps,
#         install: true,
#     )
# endif
#
# install_headers(uno_headers, install_dir: 'include/uno')
