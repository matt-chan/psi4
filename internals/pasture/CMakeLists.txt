if(ENABLE_psi4pasture)
  ExternalProject_Add(psi4pasture
    DEPENDS psi4_core
    GIT_REPOSITORY https://github.com/psi4/psi4pasture
    CMAKE_ARGS -DENABLE_ccsort=${ENABLE_ccsort}
               -DENABLE_transqt2=${ENABLE_transqt2}
               -Dpsi4_DIR=${STAGED_INSTALL_PREFIX}/share/cmake/psi4
               -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}
               -DCMAKE_C_COMPILER=${CMAKE_C_COMPILER}
               -DCMAKE_CXX_COMPILER=${CMAKE_CXX_COMPILER}
    CMAKE_CACHE_ARGS -DCMAKE_C_FLAGS:STRING=${CMAKE_C_FLAGS}
                     -DCMAKE_CXX_FLAGS:STRING=${CMAKE_CXX_FLAGS}
    INSTALL_COMMAND ${CMAKE_MAKE_PROGRAM} install)
endif()
