set(PELIB_SOURCES
	conversion.cpp
	ord_lookup.cpp
	string.cpp
)

target_sources(${PROJECT_NAME} PRIVATE ${PELIB_SOURCES})

target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)

target_include_directories(${PROJECT_NAME}
	PUBLIC ${PROJECT_SOURCE_DIR}/include/)

# Disable all warnings from this library.
if(MSVC)
	target_compile_options(${PROJECT_NAME} PUBLIC "/w")
else()
	target_compile_options(${PROJECT_NAME} PUBLIC "-w")
endif()
