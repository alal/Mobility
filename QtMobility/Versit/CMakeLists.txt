project(Versit)

if(${QT_MOBILITY_VERSITORGANIZER_FOUND})
    set(VersitOrganizer_SRC
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerexporter_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerexporterdetailhandler_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerhandler_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerhandlerfactory_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerimporter_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitorganizerimporterpropertyhandler_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/versit_module_wrapper.cpp
    )
    message("Module Versit - QtVersitOrganizer extensions enabled.")
else()
    message("Module Versit - QtVersitOrganizer extensions disabled.")
    set(VersitOrganizer_SRC )
endif()

if(${QT_MOBILITY_MAJOR_VERSION} EQUAL 1 AND ${QT_MOBILITY_MINOR_VERSION} LESS 2)
    set(Versit_12_SRC )
else()
    set(Versit_12_SRC
        ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversittimezonehandler_wrapper.cpp
    )
endif()


if(${QT_MOBILITY_MAJOR_VERSION} EQUAL 1 AND ${QT_MOBILITY_MINOR_VERSION} LESS 1)
    set(Versit_11_SRC )
else()
    set(Versit_11_SRC
        ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactexporterdetailhandlerv2_wrapper.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactimporterpropertyhandlerv2_wrapper.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontacthandler_wrapper.cpp
        ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontacthandlerfactory_wrapper.cpp
        ${Versit_12_SRC}
    )
endif()

set(Versit_SRC
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactexporter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactexporterdetailhandler_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactimporter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitcontactimporterpropertyhandler_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitdefaultresourcehandler_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitdocument_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitproperty_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitreader_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitresourcehandler_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/qtmobility_qversitwriter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit/versit_module_wrapper.cpp
${Versit_11_SRC}
${VersitOrganizer_SRC}
)

set(Versit_INCLUDE_DIRECTORIES
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Versit
${Contacts_BINARY_DIR}/${BINDING_NAME}/Contacts/
${Organizer_BINARY_DIR}/${BINDING_NAME}/Organizer/
${SHIBOKEN_INCLUDE_DIR}
${PYTHON_INCLUDE_PATH}
${PYSIDE_INCLUDE_DIR}
${PYSIDE_INCLUDE_DIR}/QtCore
${PYSIDE_INCLUDE_DIR}/QtGui
${QT_INCLUDE_DIR}
${QT_QTCORE_INCLUDE_DIR}
${QT_MOBILITY_INCLUDE_DIR}
${QT_MOBILITY_PARENT_INCLUDE_DIR}
${QT_MOBILITY_CONTACTS_INCLUDE_DIR}
${QT_MOBILITY_ORGANIZER_INCLUDE_DIR}
${QT_MOBILITY_VERSIT_INCLUDE_DIR}
${QT_MOBILITY_VERSITORGANIZER_INCLUDE_DIR}
)

set(Versit_LINK_LIBRARIES
${PYTHON_LIBRARIES}
${SHIBOKEN_LIBRARY}
${PYSIDE_LIBRARY}
${QT_QTCORE_LIBRARY}
${QT_MOBILITY_CONTACTS_LIBRARY}
${QT_MOBILITY_ORGANIZER_LIBRARY}
${QT_MOBILITY_VERSIT_LIBRARY}
${QT_MOBILITY_VERSITORGANIZER_LIBRARY}
)
set(Versit_TYPESYSTEM_PATHS "${Versit_SOURCE_DIR}:${Contacts_SOURCE_DIR}")
set(Versit_TYPESYSTEM "${Versit_SOURCE_DIR}/typesystem_versit.xml")

if(${QT_MOBILITY_VERSITORGANIZER_FOUND})
    set(Versit_TYPESYSTEM_PATHS "${Versit_TYPESYSTEM_PATHS}:${Organizer_SOURCE_DIR}")
    set(Versit_TYPESYSTEM "${Versit_SOURCE_DIR}/typesystem_versitorganizer.xml")
endif()


CREATE_PYSIDE_MODULE_WITH_TYPESYSTEM(Versit
                     ${QT_MOBILITY_VERSIT_INCLUDE_DIR}:${QT_MOBILITY_CONTACTS_INCLUDE_DIR}:${QT_MOBILITY_ORGANIZER_INCLUDE_DIR}:${QT_MOBILITY_VERSITORGANIZER_INCLUDE_DIR}
                     Versit_SRC
                     Versit_INCLUDE_DIRECTORIES
                     Versit_LINK_LIBRARIES
                     Versit_TYPESYSTEM_PATHS
                     ${Versit_TYPESYSTEM})

add_dependencies(Versit Contacts Organizer)

