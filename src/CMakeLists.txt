cmake_minimum_required(VERSION 2.8.12)
project(LooseQuadtree CXX)
enable_testing()
add_compile_options(-std=c++11 -Wall -pedantic)
if(MSVC)
#add_compile_options(/WX)
else()
add_compile_options(-Wextra -Wconversion -Werror)
endif()
#add_compile_options($<$<CONFIG:Debug>:-fsanitize=address>)
#add_compile_options($<$<CONFIG:Debug>:-fsanitize=leak>)
#add_compile_options($<$<CONFIG:Debug>:-fsanitize=undefined>)
#add_compile_options($<$<CONFIG:Release>:-pg>)
include_directories(include)
add_executable(LooseQuadtreeTest test/LooseQuadtreeTest.cpp)
#set_target_properties(LooseQuadtreeTest PROPERTIES LINK_FLAGS_DEBUG "-fsanitize=address")
#set_target_properties(LooseQuadtreeTest PROPERTIES LINK_FLAGS_DEBUG "-fsanitize=leak -fsanitize=undefined")
#set_target_properties(LooseQuadtreeTest PROPERTIES LINK_FLAGS_RELEASE "-pg")
add_test(LooseQuadtreeTest LooseQuadtreeTest)

