
add_library(aliroot-lite-cdb SHARED)

target_sources(aliroot-lite-cdb PRIVATE
  AliCDBDump.cxx
  AliCDBEntry.cxx
  AliCDBGrid.cxx
  AliCDBHandler.cxx
  AliCDBId.cxx
  AliCDBLocal.cxx
  AliCDBManager.cxx
  AliCDBMetaData.cxx
  AliCDBPath.cxx
  AliCDBRunRange.cxx
  AliCDBStorage.cxx
  AliDCSSensor.cxx
  AliGRPObject.cxx
  AliSplineFit.cxx
)

target_include_directories(aliroot-lite-cdb
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_property(TARGET aliroot-lite-cdb PROPERTY PUBLIC_HEADER 
AliCDBManager.h)

target_link_libraries(aliroot-lite-cdb PUBLIC ROOT::XMLParser 
                                               ROOT::Matrix 
                                               ROOT::Minuit
                                               aliroot-lite-base)
  
root_generate_dictionary(G__AliRootLitecdb
  AliCDBDump.h
  AliCDBEntry.h
  AliCDBGrid.h
  AliCDBHandler.h
  AliCDBId.h
  AliCDBLocal.h
  AliCDBManager.h
  AliCDBMetaData.h
  AliCDBPath.h
  AliCDBRunRange.h
  AliCDBStorage.h
  AliDCSSensor.h
  AliGRPObject.h
  AliSplineFit.h
                         aliroot-lite-cdb-linkdef.h
  MODULE aliroot-lite-cdb)

install(TARGETS aliroot-lite-cdb)
