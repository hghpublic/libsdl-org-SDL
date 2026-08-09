
set(target 01-read-and-draw)
add_executable(${target})
target_sources(${target} PRIVATE
    read-and-draw.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "camera"
)
