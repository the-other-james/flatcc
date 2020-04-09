
add_library(flat_lib "SHARED"
    builder.c
    emitter.c
    refmap.c
    verifier.c
    json_parser.c
    json_printer.c
)

# Override the default behavior of attaching a "lib" prefix
set_target_properties(flat_lib PROPERTIES PREFIX "")

# Create the install targets for this shared/modular app
foreach(TGT ${APP_INSTALL_LIST})
  install(TARGETS ${APP_NAME} DESTINATION ${TGT}/${INSTALL_SUBDIR})
endforeach()

#if (FLATCC_INSTALL)
#    install(TARGETS flatccrt DESTINATION ${lib_dir})
#endif()
