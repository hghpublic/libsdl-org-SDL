
set(target 01-load-bitmaps)
add_executable(${target})
target_sources(${target} PRIVATE
    load-bitmaps.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE SDL3::SDL3)
set_target_properties(${target} PROPERTIES
    FOLDER "asyncio"
)
set(bitmaps
    "gamepad_front.png"
    "icon2x.png"
    "sample.png"
    "speaker.png"
)
foreach(bitmap IN LISTS bitmaps)
    add_custom_command(TARGET ${target} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_SOURCE_DIR}/test/${bitmap} $<TARGET_FILE_DIR:${target}>/
    )
endforeach()
