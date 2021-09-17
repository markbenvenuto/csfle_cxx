

cmake_minimum_required (VERSION 3.15)

project (csfle_cxx)

set (CMAKE_EXPORT_COMPILE_COMMANDS ON)
set (CMAKE_CXX_STANDARD 17)

# Add executable called "helloDemo" that is built from the source files
# "demo.cxx" and "demo_b.cxx". The extensions are automatically found.
add_executable (csfle_cxx sample.cpp)

# Link the executable to the Hello library. Since the Hello library has
# public include directories we will use those link directories when building
# csfle_cxx
target_link_directories (csfle_cxx PUBLIC /home/mark/src/usr/lib64)
target_compile_options(csfle_cxx PRIVATE -stdlib=libc++)
target_link_options(csfle_cxx PRIVATE -stdlib=libc++)

target_link_libraries (csfle_cxx LINK_PUBLIC bsoncxx)
target_link_libraries (csfle_cxx LINK_PUBLIC mongocxx)
target_link_libraries (csfle_cxx LINK_PUBLIC csfle_support)


target_include_directories (csfle_cxx PRIVATE /home/mark/src/usr/include)
target_include_directories (csfle_cxx PRIVATE /home/mark/src/usr/include/mongocxx/v_noabi/)
target_include_directories (csfle_cxx PRIVATE /home/mark/src/usr/include/bsoncxx/v_noabi/)
# target_compile_definitions (csfle_cxx PRIVATE ${BSON_DEFINITIONS})


