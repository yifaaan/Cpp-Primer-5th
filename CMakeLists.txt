cmake_minimum_required(VERSION 3.20)
project(Cpp-Primer-5th)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

#
# include_directories(${PROJECT_SOURCE_DIR}/include)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

# 将 src/*.cpp 存入SRC_LIST
#aux_source_directory(${PROJECT_SOURCE_DIR}/src/Chp6 SRC_LIST)
#add_executable(out ${SRC_LIST})



file(GLOB_RECURSE SOURCES "**.cpp")

foreach(FILE IN LISTS SOURCES)
	cmake_path(GET FILE STEM FILE_STEM)
	add_executable(${FILE_STEM} ${FILE})
endforeach()



#file(GLOB SOURCES "src/Chp6/*.cpp")

# foreach(source ${SOURCES})
#     # 获取文件名（不带扩展名）
#     get_filename_component(executable_name ${source} NAME_WE)
#     add_executable(${executable_name} ${source})
# endforeach()

# file(GLOB SOURCES "src/Chp6/uva816.cpp")
# add_executable(uva_executable ${SOURCES})