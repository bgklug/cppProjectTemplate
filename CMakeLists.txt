cmake_minimum_required(3.4)
project(ProjectTemplate)

find_package(<external package> <Version> REQUIRED)

add_executable(ProjectTemplate )
target_link_libraries(ProjectTemplate 
    PUBLIC  
    PRIVATE 
    )
    
    
install(TARGETS ProjectTemplate EXPORT ProjectTemplateTargets
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    RUNTIME DESTINATION bin
    INCLUDES DESTINATION includes
    )
    
install(EXPORT ProjectTemplateTargets
    FILE ProjectTemplateTargets.cmake
    NAMESPACE ProjectTemplate::
    DESTINATION lib/cmake/ProjectTemplate
    )
    
include(CMakePackageConfigHelpers)

write_basic_package_version_file("ProjectTemplateConfigVersion.cmake"
    VERSION ${ProjectTemplate_VERSION}
    COMPATIBILITY SameMajorVersion
    )
    
install(FILES "ProjectTemplateConfig.cmake" "ProjectTemplateConfigVersion.cmake"
    DESTINATION lib/cmake/ProjectTemplate
    )
