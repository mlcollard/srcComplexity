# Build for srcComplexity

cmake_minimum_required(VERSION 3.10.0)

project(srcComplexity VERSION "0.9.5")

# Build srcComplexity
add_executable(srcComplexity srcComplexity.cpp srcMLXPathCount.cpp)

# run example
set(SRCCOMPLEXITY_TESTFILE srcMLXPathCount.cpp.xml)
configure_file(${SRCCOMPLEXITY_TESTFILE} ${SRCCOMPLEXITY_TESTFILE} COPYONLY)
add_custom_target(run DEPENDS srcComplexity
                      COMMAND ./srcComplexity ${SRCCOMPLEXITY_TESTFILE})
