set(logger_SRCS
  Logger.cpp
  )

add_library(dlog_logger ${logger_SRCS})
set_target_properties(dlog_logger PROPERTIES COMPILE_FLAGS "-std=c++0x")
install(TARGETS dlog_logger DESTINATION lib)

file(GLOB HEADERS "*.h")
install(FILES ${HEADERS} DESTINATION include/dlog/logger)
target_link_libraries(dlog_logger dlog_config)
target_link_libraries(dlog_logger dlog_common)
target_link_libraries(dlog_logger pthread)
