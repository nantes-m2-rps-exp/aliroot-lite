add_library(aliroot-lite-aod SHARED)

target_sources(aliroot-lite-aod PRIVATE
  AliAODAD.cxx
  AliAODBranchReplicator.cxx
  AliAODCaloCells.cxx
  AliAODCaloCluster.cxx
  AliAODCaloTrigger.cxx
  AliAODCluster.cxx
  AliAODDimuon.cxx
  AliAODEvent.cxx
  AliAODExtension.cxx
  AliAODHMPIDrings.cxx
  AliAODHandler.cxx
  AliAODHeader.cxx
  AliAODInputHandler.cxx
  AliAODMCHeader.cxx
  AliAODMCParticle.cxx
  AliAODPid.cxx
  AliAODPid.cxx
  AliAODRecoDecay.cxx
  AliAODRedCov.cxx
  AliAODTZERO.cxx
  AliAODTrack.cxx
  AliAODTracklets.cxx
  AliAODTrdTrack.cxx
  AliAODTrdTracklet.cxx
  AliAODVZERO.cxx
  AliAODVertex.cxx
  AliAODZDC.cxx
  AliAODcascade.cxx
  AliAODpidUtil.cxx
  AliAODv0.cxx
  AliNanoAODHeader.cxx
  AliNanoAODStorage.cxx
)

target_link_libraries(aliroot-lite-aod PUBLIC aliroot-lite-esd)

target_include_directories(aliroot-lite-aod
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

set_property(TARGET aliroot-lite-aod PROPERTY PUBLIC_HEADER 
  AliAODAD.h
  AliAODBranchReplicator.h
  AliAODCaloCells.h
  AliAODCaloCluster.h
  AliAODCaloTrigger.h
  AliAODCluster.h
  AliAODDimuon.h
  AliAODEvent.h
  AliAODExtension.h
  AliAODFmdCluster.h
  AliAODHMPIDrings.h
  AliAODHandler.h
  AliAODHeader.h
  AliAODJet.h
  AliAODInputHandler.h
  AliAODMCHeader.h
  AliAODMCParticle.h
  AliAODPid.h
  AliAODPmdCluster.h
  AliAODRecoDecay.h
  AliAODRedCov.h
  AliAODTZERO.h
  AliAODTrack.h
  AliAODTracklets.h
  AliAODTrdTrack.h
  AliAODTrdTracklet.h
  AliAODVZERO.h
  AliAODVertex.h
  AliAODZDC.h
  AliAODcascade.h
  AliAODkink.h
  AliAODpidUtil.h
  AliAODpidUtil.h
  AliAODv0.h
  AliNanoAODHeader.h
  AliNanoAODStorage.h
)

root_generate_dictionary(G__AliRootLiteaod
  AliAODAD.h
  AliAODBranchReplicator.h
  AliAODCaloCells.h
  AliAODCaloCluster.h
  AliAODCaloTrigger.h
  AliAODCluster.h
  AliAODDimuon.h
  AliAODEvent.h
  AliAODExtension.h
  AliAODHMPIDrings.h
  AliAODHandler.h
  AliAODHeader.h
  AliAODInputHandler.h
  AliAODMCHeader.h
  AliAODMCParticle.h
  AliAODPid.h
  AliAODpidUtil.h
  AliAODRecoDecay.h
  AliAODRedCov.h
  AliAODTZERO.h
  AliAODTrack.h
  AliAODTracklets.h
  AliAODTrdTrack.h
  AliAODTrdTracklet.h
  AliAODVZERO.h
  AliAODVertex.h
  AliAODZDC.h
  AliAODcascade.h
  AliAODpidUtil.h
  AliAODv0.h
  AliNanoAODHeader.h
  AliNanoAODStorage.h
                         aliroot-lite-aod-linkdef.h
  MODULE aliroot-lite-aod)
 
install(TARGETS aliroot-lite-aod EXPORT aliroot-lite)

