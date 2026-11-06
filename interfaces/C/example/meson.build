# project('example',['c'])

# uno_dep = dependency('uno')

hs015 = executable(
    'hs015',
    sources: 'example_hs015.c',
    link_with: [uno_C_lib],
    # link_with: [uno_cpp_lib,uno_C_lib],
    include_directories: incdirs,
    dependencies: uno_C_lib_dep,
    # link_with: [uno_C_lib],
    # dependencies: [uno_cpp_lib],
)
