cmake_minimum_required(VERSION 3.2.3)

project(EPIC-EMOJI-PICKER)

# The following line is required only if (a) you didn't install FLTK
# or if (b) find_package can't find your installation directory because
# you installed FLTK in a non-standard location.  It points to
# (a) the base folder of the build directory, or
# (b) <fltk-install-prefix>/share/fltk
# resp., where <fltk-install-prefix> is the installation prefix you
# used to install FLTK.
# (The file FLTKConfig.cmake and others must be found in that path.)

# change this for your system
set(FLTK_DIR /run/media/husky/epic_disk/OSS/fltk-1.3.8/build/)

find_package(FLTK REQUIRED NO_MODULE)

add_executable(EPIC-EMOJI-PICKER WIN32 MACOSX_BUNDLE Interface.cpp)
if (APPLE)
    target_link_libraries(EPIC-EMOJI-PICKER "-framework cocoa")
endif (APPLE)

target_include_directories(EPIC-EMOJI-PICKER PUBLIC ${FLTK_INCLUDE_DIRS})

target_link_libraries(EPIC-EMOJI-PICKER fltk)