
add_library(backoffxx INTERFACE)

target_sources(backoffxx
  INTERFACE
    attempt.h
    backoff.h
    backoffxx.h
    policies.h

  $<$<BOOL:${WIN32}>:
  >

  $<$<NOT:$<BOOL:${WIN32}>>:
  >
)

target_include_directories(backoffxx
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/../
)

target_link_libraries(backoffxx
)

target_compile_definitions(backoffxx
  INTERFACE
    $<$<BOOL:${WIN32}>:
      _UNICODE
      UNICODE
      NOMINMAX
    >

    $<$<CONFIG:DEBUG>:
      _DEBUG
    >
)

