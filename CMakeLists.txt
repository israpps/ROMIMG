cmake_minimum_required(VERSION 3.10)

# set the project name
project(ROMIMG)

# add the executable
include_directories(src)
add_executable(ROMIMG 
				src/ELF.h
				src/main.c
				src/platform.c
				src/romimg.c
				src/SonyRX.c
)