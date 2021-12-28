add_library(aliroot-lite-ana-alice SHARED)

target_sources(aliroot-lite-ana-alice PRIVATE
  AliAnalysisAlien.cxx
  AliAnalysisCuts.cxx
  AliAnalysisTaskSE.cxx
  AliESDtrackCuts.cxx
  AliMultiInputEventHandler.cxx
  AliTrackSelectionFactory.cxx
  AliVTrackSelection.cxx
)

target_link_libraries(aliroot-lite-ana-alice PUBLIC 
  aliroot-lite-ana-base
  aliroot-lite-aod
  aliroot-lite-esd)

target_include_directories(aliroot-lite-ana-alice
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_property(TARGET aliroot-lite-ana-alice PROPERTY PUBLIC_HEADER 
  AliAnalysisAlien.h
  AliAnalysisCuts.h
  AliAnalysisTaskSE.h
  AliESDtrackCuts.h
  AliMultiInputEventHandler.h
  AliTrackSelectionFactory.h
  AliVTrackSelection.h
)

root_generate_dictionary(G__AliRootLiteAnaAlice
  AliAnalysisAlien.h
  AliAnalysisCuts.h
  AliAnalysisTaskSE.h
  AliESDtrackCuts.h
  AliMultiInputEventHandler.h
  AliTrackSelectionFactory.h
  AliVTrackSelection.h
                         aliroot-lite-ana-alice-linkdef.h
  MODULE aliroot-lite-ana-alice)
 
install(TARGETS aliroot-lite-ana-alice)

