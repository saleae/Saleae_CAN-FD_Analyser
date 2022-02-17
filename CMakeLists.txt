cmake_minimum_required (VERSION 3.13)

project(CAN_FDAnalyzer)

add_definitions( -DLOGIC2 )

# enable generation of compile_commands.json, helpful for IDEs to locate include files.
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
source/CAN_FDAnalyzer.cpp
source/CAN_FDAnalyzer.h
source/CAN_FDAnalyzerResults.cpp
source/CAN_FDAnalyzerResults.h
source/CAN_FDAnalyzerSettings.cpp
source/CAN_FDAnalyzerSettings.h
source/CAN_FDSimulationDataGenerator.cpp
source/CAN_FDSimulationDataGenerator.h
)

add_analyzer_plugin(${PROJECT_NAME} SOURCES ${SOURCES})
