	set(PELIB_SOURCES
	BoundImportDirectory.cpp
	CoffSymbolTable.cpp
	ComHeaderDirectory.cpp
	ConfigDirectory.cpp
	DebugDirectory.cpp
	ExportDirectory.cpp
	IatDirectory.cpp
	InputBuffer.cpp
	OutputBuffer.cpp
	PeFile.cpp
	PeLibAux.cpp
	RelocationsDirectory.cpp
	ResourceDirectory.cpp
	RichHeader.cpp
	SecurityDirectory.cpp
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
