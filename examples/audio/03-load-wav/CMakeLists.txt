
set(target 03-load-wav)
add_executable(${target})
target_sources(${target} PRIVATE
    load-wav.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "audio"
)
add_custom_command(TARGET ${target} POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/test/sample.wav $<TARGET_FILE_DIR:${target}>/
)
