# incdirs += [include_directories('.')]

# fortran_interface_h = custom_target(
#     'gen-fortran-header',
#     output: 'fortran_interface.h',
#     command: [
#         'echo',
#         '''"
# #ifndef FC_HEADER_INCLUDED
# #define FC_HEADER_INCLUDED

# /* Mangling for Fortran global symbols without underscores. */
# #define FC_GLOBAL(name,NAME) name##_

# /* Mangling for Fortran global symbols with underscores. */
# #define FC_GLOBAL_(name,NAME) name##_

# /* Mangling for Fortran module symbols without underscores. */
# #define FC_MODULE(mod_name,name, mod_NAME,NAME) __##mod_name##_MOD_##name

# /* Mangling for Fortran module symbols with underscores. */
# #define FC_MODULE_(mod_name,name, mod_NAME,NAME) __##mod_name##_MOD_##name

# #endif
# "''',
#         '>',
#         '@OUTPUT@',
#     ],
#     install: true,
#     install_dir: 'uno',
# )
# uno_sources += [fortran_interface_h]

uno_headers += [
    files(
        'BLAS.hpp',
        'BLASMatrix.hpp',
        # 'BLASVector.hpp',
        # 'COOSparsity.hpp',
        'DenseMatrix.hpp',
        'Indexing.hpp',
        'LAPACK.hpp',
        'LAPACK_extension.hpp',
        # 'MatrixOrder.hpp',
        'Norm.hpp',
        'SparseVector.hpp',
        'Vector.hpp',
        'View.hpp',
        'fortran_interface.h',
    ),
]
uno_sources += [
    files(
        'BLAS.hpp',
        'BLASMatrix.hpp',
        # 'BLASVector.hpp',
        # 'COOSparsity.hpp',
        'DenseMatrix.hpp',
        'Indexing.hpp',
        'LAPACK.hpp',
        'LAPACK_extension.hpp',
        #'MatrixOrder.hpp',
        'Norm.hpp',
        'SparseVector.hpp',
        'Vector.hpp',
        'View.hpp',
    ),
]
