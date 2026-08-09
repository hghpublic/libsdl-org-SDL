
set(target 06-textures)
add_executable(${target})
target_sources(${target} PRIVATE
    textures.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "renderer"
)
add_custom_command(TARGET ${target} POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/test/sample.png $<TARGET_FILE_DIR:${target}>/
)
