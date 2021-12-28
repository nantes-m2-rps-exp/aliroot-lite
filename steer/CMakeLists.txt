add_library(aliroot-lite-steer SHARED)

target_sources(aliroot-lite-steer PRIVATE
  AliDCSArray.cxx
  AliLHCData.cxx
  AliLHCDipValT.cxx
  AliLHCReader.cxx
  AliTriggerRunScalers.cxx
)


target_link_libraries(aliroot-lite-steer PUBLIC aliroot-lite-esd)

target_include_directories(aliroot-lite-steer
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_property(TARGET aliroot-lite-steer PROPERTY PUBLIC_HEADER 
  AliLHCData.h
  AliLHCDipValT.h
  AliTriggerRunScalers.h
)

root_generate_dictionary(G__AliRootLiteSteer
  AliDCSArray.h
  AliLHCData.h
  AliLHCDipValT.h
  AliLHCReader.h
  AliTriggerRunScalers.h
                         aliroot-lite-steer-linkdef.h
  MODULE aliroot-lite-steer)
 
install(TARGETS aliroot-lite-steer EXPORT aliroot-lite)

