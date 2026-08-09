
set(target 04-multiple-streams)
add_executable(${target})
target_sources(${target} PRIVATE
    multiple-streams.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "audio"
)
set(sounds
    sample.wav
    sword.wav
)
foreach(sound IN LISTS sounds)
    add_custom_command(TARGET ${target} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/test/${sound} $<TARGET_FILE_DIR:${target}>/
    )
endforeach()
