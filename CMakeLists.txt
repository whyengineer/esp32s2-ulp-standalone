cmake_minimum_required(VERSION 3.5)
# CMake toolchain file for ULP-RISC-V
set(CMAKE_SYSTEM_NAME Generic)

# Not best solution, needs to figure why the compiler detection
# fails in CI
set(CMAKE_C_COMPILER_FORCED TRUE)
set(CMAKE_CXX_COMPILER_FORCED TRUE)

set(CMAKE_C_COMPILER "riscv-none-embed-gcc")
set(CMAKE_ASM_COMPILER "riscv-none-embed-gcc")
set(CMAKE_CXX_COMPILER "riscv-none-embed-g++")

set( CMAKE_AR "riscv-none-embed-ar" CACHE FILEPATH "Archiver" )

set(CMAKE_C_FLAGS "-Os -march=rv32imc -mdiv -fdata-sections -ffunction-sections")
set(CMAKE_ASM_FLAGS "-march=rv32imc -mdiv -x assembler-with-cpp -fdata-sections -ffunction-sections")
set(CMAKE_EXE_LINKER_FLAGS "-march=rv32imc --specs=nano.specs --specs=nosys.specs")


set(ULP_LIB_NAME "mylib")


add_library(${ULP_LIB_NAME} STATIC 
    source/testlib.c
)

target_include_directories(${ULP_LIB_NAME} PRIVATE include)

project(${ULP_LIB_NAME})