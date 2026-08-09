
set(target 02-clipboard)
add_executable(${target})
target_sources(${target} PRIVATE
    clipboard.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "misc"
)
