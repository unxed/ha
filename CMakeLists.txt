cmake_minimum_required(VERSION 3.2.3)
project(ha)

set(CMAKE_C_FLAGS
	"-std=c99 -D_DEFAULT_SOURCE -D_GNU_SOURCE -W -Wall -Wextra -pedantic -Wwrite-strings -Winit-self -Wcast-qual -Wpointer-arith -Wstrict-aliasing -Wformat=2 -Wmissing-declarations -Wmissing-include-dirs -Wno-unused-parameter -Wuninitialized -Wold-style-definition -Wstrict-prototypes -Wmissing-prototypes")
set(CMAKE_C_FLAGS_DEBUG "-O0 -g -ggdb")
set(CMAKE_C_FLAGS_RELEASE "-O3 -march=native")

include_directories(include)

add_executable(ha
	acoder.c
	archive.c
	asc.c
	cpy.c
	error.c
	ha.c
	haio.c
	hsc.c
	info.c
	machine.c
	misc.c
	swdict.c)

install(TARGETS ha DESTINATION bin)
install(FILES doc/FORMAT doc/MD_FUNCS.TXT COPYING README.md README.orig DESTINATION share/doc/ha)

