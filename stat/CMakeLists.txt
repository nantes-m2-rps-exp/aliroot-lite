
add_library(aliroot-lite-stat SHARED)

target_sources(aliroot-lite-stat PRIVATE
  AliMathBase.cxx
  AliNDLocalRegression.cxx
  TTreeStream.cxx
)

target_link_libraries(aliroot-lite-stat PUBLIC 
  ROOT::Hist 
  ROOT::Minuit
  ROOT::Physics
  ROOT::Tree
)

target_include_directories(aliroot-lite-stat
    PUBLIC
            $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    INTERFACE
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)

# set_property(TARGET aliroot-lite-stat PROPERTY PUBLIC_HEADER 
# )

root_generate_dictionary(G__AliRootLitestat
  AliMathBase.h
  AliNDLocalRegression.h
  TTreeStream.h
                         aliroot-lite-stat-linkdef.h
  MODULE aliroot-lite-stat)
 
install(TARGETS aliroot-lite-stat)

