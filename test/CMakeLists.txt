
include_directories(

    # Directory containing the main project source files.
    ${PROJECT_SOURCE_DIR}/src 
    
    # Directory containing EzTest source files.
    eztest
)

add_executable(eztest_runner    

    # EzTest
    eztest/eztest.h
    eztest/runner.c
    
    # Unit test files
        
)

target_link_libraries(eztest_runner 

    # Add the libraries under test here.
    my_library # This is the library created in the src directory.
)

