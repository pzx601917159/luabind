# Copyright (C) 2007-2012 LuaDist.
# Modified by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.
# Original build script by Leandro Motta Barros.

project ( luabind C CXX )
cmake_minimum_required ( VERSION 2.8 )

# Include directories
include_directories ( ${Boost_INCLUDE_DIRS} ${LUA_INCLUDE_DIR} ${CMAKE_CURRENT_SOURCE_DIR} )

# Link directories
#~ 	LINK_DIRECTORIES(${BOOST_LIBRARY_DIRS})

# Build the library
file ( GLOB LUABIND_SRC "src/*.cpp" )

add_definitions ( -DLUABIND_BUILDING )

add_library ( luabind ${LUABIND_SRC} )
target_link_libraries ( luabind ${LUA_LIBRARIES} )

