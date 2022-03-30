cmake_minimum_required(VERSION 3.23.0)

project(hello-world)
set (SRCS src/main.c)
set (EXEC_NAME hello-world)
set (CMAKE_C_FLAGS "-Wall -Werror -Wextra")
set (CMAKE_EXPORT_COMPILE_COMMANDS ON) #vscode include path checking

add_custom_target(fclean make clean)
add_custom_target(re make clean COMMAND make)

add_executable(${EXEC_NAME} ${SRCS})

# add_subdirectory(lib/libft)
# target_link_libraries(${EXEC_NAME} PRIVATE ft)

target_include_directories(${EXEC_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)