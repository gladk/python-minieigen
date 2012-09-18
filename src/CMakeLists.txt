SET(DCSRC "double-conversion/bignum.cc;double-conversion/bignum-dtoa.cc;double-conversion/cached-powers.cc;double-conversion/diy-fp.cc;double-conversion/double-conversion.cc;double-conversion/fast-dtoa.cc;double-conversion/fixed-dtoa.cc;double-conversion/strtod.cc")

ADD_LIBRARY(minieigen SHARED miniEigen.cpp ${DCSRC})
SET_TARGET_PROPERTIES(minieigen
PROPERTIES
    SOVERSION 0.2
    VERSION 0.2
    OUTPUT_NAME minieigen
    PREFIX ""
)
TARGET_LINK_LIBRARIES(minieigen ${Boost_LIBRARIES} ${PYTHON_LIBRARIES})

INSTALL(TARGETS minieigen LIBRARY DESTINATION ${LIBRARY_OUTPUT_PATH})
