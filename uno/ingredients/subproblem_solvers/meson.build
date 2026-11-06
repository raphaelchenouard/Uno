# incdirs = [include_directories('.')]

uno_headers += [
    files(
        'LPSolver.hpp',
        'BoxLPSolver.hpp',
        'COOLinearSystem.hpp',
        'DirectSymmetricIndefiniteLinearSolver.hpp',
        'EQPSolver.hpp',
        'InverseNewtonSolver.hpp',
        'IQPSolver.cpp',
        'KKTSystemDumper.hpp',
        'LPSolverFactory.hpp',
        'LinearSystem.hpp',
        'LowRankCorrection.hpp',
        'LPSolverFactory.hpp',
        'QPSolver.hpp',
        'QPSolverFactory.hpp',
        'QuadraticProgram.hpp',
        'SolverWorkspace.hpp',
        'SubproblemSolver.hpp',
        'SubproblemSolverFactory.hpp',
        'SubproblemStatus.hpp',
        'SymmetricIndefiniteLinearSolver.hpp',
        'SymmetricIndefiniteLinearSolverFactory.hpp',
        # 'WoodburyEQPSolver.hpp',
    ),
]
uno_sources += [
    files(
        'BoxLPSolver.cpp',
        'COOLinearSystem.cpp',
        'EQPSolver.cpp',
        'InverseNewtonSolver.cpp',
        'IQPSolver.cpp',
        'KKTSystemDumper.cpp',
        'LowRankCorrection.cpp',
        'LPSolver.cpp',
        'LPSolverFactory.cpp',
        'QPSolver.cpp',
        'QPSolverFactory.cpp',
        'QuadraticProgram.cpp',
        # 'SubproblemSolver.cpp',
        'SymmetricIndefiniteLinearSolverFactory.cpp',
        # 'WoodburyEQPSolver.cpp',
    ),
]

if bqpd_dep.found()
    subdir('BQPD')
endif
if highs_dep.found()
    subdir('HiGHS')
endif
if hsl_dep.found()
  subdir('HSL')
endif
if ma27_dep.found()
    subdir('MA27')
endif
if ma57_dep.found()
    subdir('MA57')
endif
if ma86_dep.found()
    subdir('MA86')
endif
if mumps_dep.found()
    subdir('MUMPS')
endif
if spral_dep.found()
    subdir('SSIDS')
endif
