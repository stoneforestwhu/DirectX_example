# cmake minimum version required
cmake_minimum_required (VERSION 2.8)
# project information

project (TestTriangle)

# for win32 project
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /SUBSYSTEM:WINDOWS")

# Dx11 SDK install directory
set(DIRECT_HOME "C:/Program Files\ (x86)/Microsoft\ DirectX\ SDK\ (June 2010)")
set(DIRECT_UT_HOME "${DIRECT_HOME}/Samples/C++/DXUT11")

# set charactor set for project
add_definitions(-DUNICODE -D_UNICODE)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/inc
                    ${DIRECT_HOME}/Include
                    ${DIRECT_UT_HOME}/Core 
                    ${DIRECT_UT_HOME}/Optional)
					
link_directories(${DIRECT_HOME}/Lib/x64)

add_executable(test_triangle src/triangle.cpp)
target_link_libraries(test_triangle d3d11.lib d3dcompiler.lib d3dx11d.lib d3dx9d.lib dxerr.lib dxguid.lib)