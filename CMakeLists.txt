cmake_minimum_required(3.4)
project(ProjectTemplate)

find_package(<external package> <Version> REQUIRED)

add_executable(ProjectTemplate )
target_link_libraries(ProjectTemplate 
    PUBLIC  
    PRIVATE 
    )
    
    
