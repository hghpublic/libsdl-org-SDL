
set(target 04-gamepad-events)
add_executable(${target})
target_sources(${target} PRIVATE
    gamepad-events.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "input"
)
