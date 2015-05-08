
cmake_minimum_required(VERSION 2.8.11)
list(APPEND CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)

# Package management ###########################################################

include(HunterGate)

# HunterGate(
#     URL "https://github.com/alamaison/hunter/archive/892a63851222018f0b4beb262b740020c9cba4e6.tar.gz"
#     SHA1 "1adf2b8cd773cb3fe123fe454098e8c221f09ead"
# )
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.10.1.tar.gz"
    SHA1 "8438f646010f12128755f2703fd325ec2369e938"
)

hunter_add_package(TIFF)

################################################################################

project(tiff-test)

add_executable(foo foo.cpp)

find_package(TIFF REQUIRED)

target_link_libraries(foo PRIVATE ${TIFF_LIBRARIES})
