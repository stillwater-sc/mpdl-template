cmake_minimum_required(VERSION 3.22)
set(app_name polynomial)
project(${app_name} CXX)

# Universal is a C++ header-only library, so we do not need to build anything
include_directories(${MPDL_ROOT_DIR}/ext/stillwater-sc/universal/include)

# source files that make up the command
set(SOURCE_FILES
	integers.cpp
	fixpnts.cpp
	areals.cpp
	cfloats.cpp
	posits.cpp
	logs.cpp
	unums.cpp
	main.cpp
)

add_executable(${app_name} ${SOURCE_FILES})
set(folder "Applications/Mixed-Precision")
set_target_properties(${app_name} PROPERTIES FOLDER ${folder})

# add libraries if you need them
#target_link_libraries(${app_name} required-library1 required-library2)
install(TARGETS ${app_name} DESTINATION ${MPDL_INSTALL_BIN_DIR})
#install(FILES my-consolidated-include.hpp DESTINATION ${MPDL_INSTALL_INCLUDE_DIR})
