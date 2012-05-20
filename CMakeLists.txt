# Copyright (c) 2012 Marwan Abdellah <abdellah.marwan@gmail.com>

# Minimum required CMake version 
cmake_minimum_required(VERSION 2.6)

# FFT 
PROJECT(FFT)

# Add CMake modules 
SET(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/CMake)

# FFTW 
SET(FFTW_ROOT ${PROJECT_SOURCE_DIR}/../install) 
FIND_PACKAGE(FFTW REQUIRED)

# Add the heade files to the include directories
INCLUDE_DIRECTORIES("${FFTW_INCLUDE_DIR}")

# Generate the executable 
ADD_EXECUTABLE(FFT FFT.cxx)

# Link aginst the FFTW libraries 
TARGET_LINK_LIBRARIES(FFT ${FFTW_LIBRARIES})

# Packaging 
include(CPackConfig)
