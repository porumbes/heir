cmake_minimum_required(VERSION 3.19.1 FATAL_ERROR)

project(Heir
	VERSION 0.0.1
	LANGUAGES C CXX)

#
# Compiler Requirements
#
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

#
# External Content to Fetch
#

include(FetchContent)

# OpenMesh
set(OPENMESH_DOCS false CACHE BOOL "Enable or disable building of documentation")
FetchContent_Declare(openmesh
    GIT_REPOSITORY https://www.graphics.rwth-aachen.de:9000/OpenMesh/OpenMesh.git
    GIT_TAG        OpenMesh-10.0
)
FetchContent_MakeAvailable(openmesh)

# PolyScope
FetchContent_Declare(polyscope
    GIT_REPOSITORY https://github.com/nmwsharp/polyscope.git
    GIT_SUBMODULES_RECURSE TRUE
)
FetchContent_MakeAvailable(polyscope)

#
# Executables and Targets
#
add_executable(heir 
    main.cpp
)

target_include_directories(heir PRIVATE ${OpenMesh_SOURCE_DIR}/src)

target_link_libraries(heir
    OpenMeshCore
    polyscope
)
