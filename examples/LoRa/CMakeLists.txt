cmake_minimum_required(VERSION 2.6)

PROJECT(lora_examples)

INCLUDE(CheckFunctionExists)

INCLUDE_DIRECTORIES(../../libraries/arduPiLoRa ../../arduPi-api ../../arduPi .)

SET(CMAKE_SHARED_LIBRARY_LINK_C_FLAGS "")
ADD_DEFINITIONS(-Os -Wall -Wmissing-declarations --std=gnu99  -g)
# -Werror

SET(API_SOURCES ../../libraries/arduPiLoRa/arduPiLoRa.cpp ../../arduPi/arduPi.cpp ../../arduPi-api/arduPiUtils.cpp ../../arduPi-api/arduPiMultiprotocol.cpp)

SET(SOURCES SX_00_CONFIG_LoRa.cpp)



ADD_EXECUTABLE(lora_config ${SOURCES} ${API_SOURCES})

TARGET_LINK_LIBRARIES(lora_config ${LIBS} pthread)


