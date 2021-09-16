set(STORAGE_CONVERSIONS 219)

if("${FLAVOUR}" STREQUAL "tpro")
  set(STORAGE_CONVERSIONS 221)
endif()
message("Storage conversion: ${STORAGE_CONVERSIONS}")

if(STORAGE_CONVERSIONS)
  add_definitions(-DSTORAGE_CONVERSIONS=${STORAGE_CONVERSIONS})
  set(SRC
    ${SRC}
    storage/conversions/conversions.cpp
    storage/conversions/conversions_219_220.cpp
    storage/conversions/conversions_220_221.cpp
    )

  include(storage/conversions/yaml/CMakeLists.txt)
endif()
