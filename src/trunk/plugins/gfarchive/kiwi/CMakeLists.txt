FIND_PACKAGE(HDF5)

IF (HDF5_FOUND)
	SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DH5_USE_16_API")
	SET(
		KIWI_SOURCES
			chunk.cpp
			db.cpp
			kiwiarchive.cpp
	)

	INCLUDE_DIRECTORIES(${HDF5_INCLUDE_DIRS})
	SC_ADD_PLUGIN_LIBRARY(KIWI kiwi "")
	SC_LINK_LIBRARIES(kiwi ${HDF5_LIBRARIES} ${Boost_filesystem_LIBRARY})
	SC_LINK_LIBRARIES_INTERNAL(kiwi core)
ENDIF (HDF5_FOUND)
