
set(target 03-gamepad-polling)
add_executable(${target})
target_sources(${target} PRIVATE
    gamepad-polling.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "input"
)
add_custom_command(TARGET ${target} POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/test/gamepad_front.png $<TARGET_FILE_DIR:${target}>/
)
