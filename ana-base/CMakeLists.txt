add_library(aliroot-lite-ana-base SHARED)

target_sources(aliroot-lite-ana-base PRIVATE
  AliAnalysisDataContainer.cxx
  AliAnalysisDataSlot.cxx
  AliAnalysisGrid.cxx
  AliAnalysisManager.cxx
  AliAnalysisSelector.cxx
  AliAnalysisStatistics.cxx
  AliAnalysisTask.cxx
  AliAnalysisTaskCfg.cxx
  AliDirList.cxx
)

target_link_libraries(aliroot-lite-ana-base PUBLIC aliroot-lite-base)

target_include_directories(aliroot-lite-ana-base
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_property(TARGET aliroot-lite-ana-base PROPERTY PUBLIC_HEADER 
  AliAnalysisDataContainer.h
  AliAnalysisDataSlot.h
  AliAnalysisGrid.h
  AliAnalysisManager.h
  AliAnalysisSelector.h
  AliAnalysisStatistics.h
  AliAnalysisTask.h
  AliAnalysisTaskCfg.h
  AliDirList.h
)

root_generate_dictionary(G__AliRootLiteAnaBase
  AliAnalysisDataContainer.h
  AliAnalysisDataSlot.h
  AliAnalysisManager.h
  AliAnalysisGrid.h
  AliAnalysisSelector.h
  AliAnalysisStatistics.h
  AliAnalysisTask.h
  AliAnalysisTaskCfg.h
  AliDirList.h
                         aliroot-lite-ana-base-linkdef.h
  MODULE aliroot-lite-ana-base)
 
install(TARGETS aliroot-lite-ana-base EXPORT aliroot-lite)

