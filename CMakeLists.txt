cmake_minimum_required(VERSION 3.28)
project(OhSweetWampum)

file(GLOB SOURCE_FILES "include/*.h" "include/*.cpp" "src/*.h" "src/*.cpp")

add_executable(${PROJECT_NAME} ${SOURCE_FILES})

find_library(DISCORD_GAME_SDK 
NAMES discord_game_sdk discord_game_sdk.dll
HINTS lib/ ./
REQUIRED)

target_link_libraries(${PROJECT_NAME} ${DISCORD_GAME_SDK})