cmake_minimum_required(VERSION 3.20)
project(CmakeTest)

set(CMAKE_CXX_STANDARD 17)

# =====================================
# Assimp options (submodule use)
# =====================================
set(ASSIMP_INSTALL OFF CACHE BOOL "" FORCE)
set(ASSIMP_BUILD_ASSIMP_TOOLS OFF CACHE BOOL "" FORCE)
set(ASSIMP_BUILD_SAMPLES OFF CACHE BOOL "" FORCE)
set(ASSIMP_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(ASSIMP_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(ASSIMP_WARNINGS_AS_ERRORS OFF CACHE BOOL "" FORCE)
set(ASSIMP_BUILD_ZLIB ON CACHE BOOL "" FORCE)

# ⚠ 不要または危険なオプションは削除（下で説明）
# set(ASSIMP_NO_EXPORT OFF CACHE BOOL "" FORCE)
# set(ASSIMP_BUILD_ALL_IMPORTERS_BY_DEFAULT ON CACHE BOOL "" FORCE)

# =====================================
# Add Assimp submodule
# =====================================
add_subdirectory(extern/assimp)

# =====================================
# Your executable
# =====================================
add_executable(MyApp
    src/main.cpp
)

# Link Assimp
target_link_libraries(MyApp PRIVATE assimp)

# Include directory for Assimp
target_include_directories(MyApp PRIVATE
    ${ASSIMP_INCLUDE_DIR}
)
