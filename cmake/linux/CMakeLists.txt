# This file is part of LAAF, a fork of LMMS.
# Modified on 2025-09-17: Updated XML file reference from lmms.xml to laaf.xml
# LAAF is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 2 of the License, or
# (at your option) any later version.
#
# LAAF is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with LAAF.  If not, see <https://www.gnu.org/licenses/>.

install(DIRECTORY icons/ DESTINATION "${DATA_DIR}/icons/hicolor")
install(FILES lmms.desktop DESTINATION "${DATA_DIR}/applications")
install(FILES laaf.xml DESTINATION "${DATA_DIR}/mime/packages")

# Preserve old CPack behavior
if(WANT_CPACK_TARBALL)
	message(STATUS "Skipping AppImage creation")
	return()
endif()

# Standard CPack options
set(CPACK_GENERATOR "External" PARENT_SCOPE)
set(CPACK_EXTERNAL_ENABLE_STAGING true PARENT_SCOPE)
set(CPACK_PACKAGE_FILE_NAME "${CMAKE_PROJECT_NAME}-${VERSION}-linux-${CMAKE_SYSTEM_PROCESSOR}")
set(CPACK_PACKAGE_FILE_NAME "${CPACK_PACKAGE_FILE_NAME}" PARENT_SCOPE)
set(CPACK_PRE_BUILD_SCRIPTS "${CMAKE_CURRENT_SOURCE_DIR}/LinuxDeploy.cmake" PARENT_SCOPE)

# Custom vars to expose to Cpack
# must be prefixed with "CPACK_" per https://stackoverflow.com/a/46526757/3196753)
set(CPACK_CURRENT_BINARY_DIR "${CMAKE_CURRENT_BINARY_DIR}" PARENT_SCOPE)
set(CPACK_CURRENT_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}" PARENT_SCOPE)
set(CPACK_BINARY_DIR "${CMAKE_BINARY_DIR}" PARENT_SCOPE)
set(CPACK_SOURCE_DIR "${CMAKE_SOURCE_DIR}" PARENT_SCOPE)
set(CPACK_QMAKE_EXECUTABLE "${QT_QMAKE_EXECUTABLE}" PARENT_SCOPE)
set(CPACK_CARLA_LIBRARIES "${CARLA_LIBRARIES}" PARENT_SCOPE)
set(CPACK_WINE_32_LIBRARY_DIRS "${WINE_32_LIBRARY_DIRS}" PARENT_SCOPE)
set(CPACK_WINE_64_LIBRARY_DIRS "${WINE_64_LIBRARY_DIRS}" PARENT_SCOPE)
set(CPACK_PROJECT_NAME "${PROJECT_NAME}" PARENT_SCOPE)
set(CPACK_PROJECT_NAME_UCASE "${PROJECT_NAME_UCASE}" PARENT_SCOPE)
set(CPACK_PROJECT_VERSION "${VERSION}" PARENT_SCOPE)
set(CPACK_CMAKE_COMMAND "${CMAKE_COMMAND}" PARENT_SCOPE)
set(CPACK_SUIL_MODULES "${Suil_MODULES}" PARENT_SCOPE)
set(CPACK_SUIL_MODULES_PREFIX "${Suil_MODULES_PREFIX}" PARENT_SCOPE)
set(CPACK_STK_RAWWAVE_ROOT "${STK_RAWWAVE_ROOT}" PARENT_SCOPE)

# TODO: Canidate for DetectMachine.cmake
if(IS_X86_64)
	set(CPACK_TARGET_ARCH x86_64 PARENT_SCOPE)
elseif(IS_X86)
	set(CPACK_TARGET_ARCH i386 PARENT_SCOPE)
elseif(IS_ARM64)
	set(CPACK_TARGET_ARCH aarch64 PARENT_SCOPE)
elseif(IS_ARM32)
	set(CPACK_TARGET_ARCH armhf PARENT_SCOPE)
else()
	set(CPACK_TARGET_ARCH unknown PARENT_SCOPE)
endif()

if(CMAKE_VERSION VERSION_LESS "3.19")
	message(WARNING "AppImage creation requires at least CMake 3.19")
endif()