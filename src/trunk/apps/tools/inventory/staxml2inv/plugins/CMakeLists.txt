INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/..)

AUX_SOURCE_DIRECTORY(../stationxml LIBSTAXML_SOURCES)

SET(EXPORTER_STAXML_SOURCES exporter.cpp ../convert2staxml.cpp ${LIBSTAXML_SOURCES})

SC_ADD_PLUGIN_LIBRARY(EXPORTER_STAXML staxml "")

SC_LINK_LIBRARIES_INTERNAL(staxml client)
