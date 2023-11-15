Acmake_minimum_required(VERSION 3.19.1 FATAL_ERROR)

project(Heir
	VERSION 0.0.1
	LANGUAGES C CXX)

include(FetchContent)

# OpenMesh
set(OPENMESH_DOCS false CACHE BOOL "Enable or disable building of documentation")
FetchContent_Declare(openmesh
    GIT_REPOSITORY https://www.graphics.rwth-aachen.de:9000/OpenMesh/OpenMesh.git
    GIT_TAG        OpenMesh-10.0
)
FetchContent_MakeAvailable(openmesh)


