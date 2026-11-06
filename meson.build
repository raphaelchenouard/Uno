project(
    'Uno',
    ['cpp', 'c', 'fortran'],
    version: '2.9.0',
    default_options: ['cpp_std=c++17'],
)

build_shared = get_option('BUILD_SHARED_LIBS')
build_static = get_option('BUILD_STATIC_LIBS')

if not (build_shared or build_static)
    error('At least one of BUILD_SHARED_LIBS or BUILD_STATIC_LIBS must be true.')
endif

bqpd_path = get_option('BQPD')
ma27_path = get_option('MA27')
ma57_path = get_option('MA57')
ma86_path = get_option('MA86')
# asl_path = get_option('AMPLSOLVER')
highs_path = get_option('HIGHS')
hsl_path = get_option('HSL')
# metis_path = get_option('METIS')
mumps_path = get_option('MUMPS')
spral_path = get_option('SPRAL')

highs_dep = dependency('', required: false)
bqpd_dep = dependency('', required: false)
hsl_dep = dependency('', required: false)
ma27_dep = dependency('', required: false)
ma57_dep = dependency('', required: false)
ma86_dep = dependency('', required: false)
asl_dep = dependency('', required: false)
metis_dep = dependency('', required: false)
mumps_dep = dependency('', required: false)
spral_dep = dependency('', required: false)

cpp_comp = meson.get_compiler('cpp')
fc = meson.get_compiler('fortran')

# Optional dependencies
if not (hsl_path == '')
    hsl_dep = cpp_comp.find_library('hsl', dirs: hsl_path, required: true)
else
    hsl_dep = dependency('hsl', required: false)
    if not hsl_dep.found()
        hsl_dep = cpp_comp.find_library('hsl', required: false)
    endif
    if not (ma57_path == '')
        ma57_dep = cpp_comp.find_library('ma57', dirs: ma57_path, required: true)
    else
        ma57_dep = dependency('ma57', required: false)
        if not ma57_dep.found()
            ma57_dep = cpp_comp.find_library('ma57', required: false)
        endif
    endif
    if not (ma27_path == '')
        ma27_dep = cpp_comp.find_library('ma27', dirs: ma27_path, required: true)
    else
        ma27_dep = dependency('ma27', required: false)
        if not ma27_dep.found()
            ma27_dep = cpp_comp.find_library('ma27', required: false)
        endif
    endif
    if not (ma86_path == '')
        ma86_dep = cpp_comp.find_library('ma86', dirs: ma86_path, required: true)
    else
        ma86_dep = dependency('ma86', required: false)
        if not ma86_dep.found()
            ma86_dep = cpp_comp.find_library('ma86', required: false)
        endif
    endif
endif
if not hsl_dep.found()
    if not (ma57_path == '')
        ma57_dep = cpp_comp.find_library('ma57', dirs: ma57_path, required: true)
    else
        ma57_dep = dependency('ma57', required: false)
        if not ma57_dep.found()
            ma57_dep = cpp_comp.find_library('ma57', required: false)
        endif
    endif
    if not (ma27_path == '')
        ma27_dep = cpp_comp.find_library('ma27', dirs: ma27_path, required: true)
    else
        ma27_dep = dependency('ma27', required: false)
        if not ma27_dep.found()
            ma27_dep = cpp_comp.find_library('ma27', required: false)
        endif
    endif
    if not (ma86_path == '')
        ma86_dep = cpp_comp.find_library('ma86', dirs: ma86_path, required: true)
    else
        ma86_dep = dependency('ma86', required: false)
        if not ma86_dep.found()
            ma86_dep = cpp_comp.find_library('ma86', required: false)
        endif
    endif
endif
# if not (metis_path == '')
#     metis_dep = cpp_comp.find_library('metis', dirs: metis_path, required: true)
# else
#     metis_dep = dependency('metis', required: false)
#     if not metis_dep.found()
#         metis_dep = cpp_comp.find_library('metis', required: false)
#     endif
# endif
if not (bqpd_path == '')
    bqpd_dep = cpp_comp.find_library('bqpd', dirs: bqpd_path, required: true)
else
    bqpd_dep = dependency('bqpd', required: false)
    if not bqpd_dep.found()
        bqpd_dep = cpp_comp.find_library('bqpd', required: false)
    endif
endif
if not (highs_path == '')
    highs_dep = cpp_comp.find_library('highs', dirs: highs_path, required: true)
else
    highs_dep = dependency('highs', required: false)
    if not highs_dep.found()
        highs_dep = cpp_comp.find_library('highs', required: false)
    endif
endif
## TODO: improve MUMPS dependency detection (variants)
if not (mumps_path == '')
    mumps_dep = cpp_comp.find_library('mumps', dirs: mumps_path, required: true)
else
    mumps_dep = dependency('mumps', required: false)
    if not mumps_dep.found()
        mumps_dep = cpp_comp.find_library('mumps', required: false)
    endif
endif
if not (spral_path == '')
    spral_dep = cpp_comp.find_library('spral', dirs: spral_path, required: true)
else
    spral_dep = dependency('spral', required: false)
    if not spral_dep.found()
        spral_dep = cpp_comp.find_library('spral', required: false)
    endif
endif

# Mandatory dependencies
lapack_dep = dependency('lapack', required: false)
if not lapack_dep.found()
    lapack_dep = cpp_comp.find_library('lapack', required: true)
endif
blas_dep = dependency('blas', required: false)
if not blas_dep.found()
    blas_dep = cpp_comp.find_library('blas', required: true)
endif

comp_args=[] # arguments added for compilation
if highs_dep.found()
  comp_args+=['-DHAS_HIGHS']
  add_project_arguments('-DHAS_HIGHS', language : ['c', 'cpp'])
endif
if bqpd_dep.found()
  comp_args+=['-DHAS_BQPD']
  add_project_arguments('-DHAS_BQPD', language : ['c', 'cpp'])
endif
if hsl_dep.found()
  comp_args+=['-DHAS_HSL','-DHAS_MA27','-DHAS_MA57']
  add_project_arguments('-DHAS_HSL','-DHAS_MA27','-DHAS_MA57', language : ['c', 'cpp'])
else
  if ma57_dep.found()
    comp_args+=['-DHAS_MA57']
    add_project_arguments('-DHAS_MA57', language : ['c', 'cpp'])
  endif
  if ma27_dep.found()
    comp_args+=['-DHAS_MA27']
    add_project_arguments('-DHAS_MA27', language : ['c', 'cpp'])
  endif
  if ma86_dep.found()
    comp_args+=['-DHAS_MA86']
    add_project_arguments('-DHAS_MA86', language : ['c', 'cpp'])
  endif
endif

uno_deps = [
    bqpd_dep,
    ma27_dep,
    ma57_dep,
    asl_dep,
    highs_dep,
    hsl_dep,
    metis_dep,
    mumps_dep,
    spral_dep,
    lapack_dep,
    blas_dep,
]

incdirs = [include_directories('.')]

subdir('uno')

subdir('interfaces')

# enable_test = get_option('ENABLE_TESTS')
# if enable_test
#     subdir('unotest')
# endif

## Generation of pkg-config file to ease dependency detection when using UNO as a library
## In your meson project, just add: uno_lib = dependency('uno')
pkgconfig = find_program('pkg-config', required: false)
if pkgconfig.found()
    pkg = import('pkgconfig')
    pkg.generate(uno_C_lib, name: 'uno', extra_cflags:comp_args)
endif
