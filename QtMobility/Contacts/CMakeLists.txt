project(Contacts)


if(${QT_MOBILITY_MAJOR_VERSION} EQUAL 1 AND ${QT_MOBILITY_MINOR_VERSION} LESS 2)
    set(Contacts_12_SRC )
else()
    set(Contacts_12_SRC
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactobserver_wrapper.cpp
    )
endif()

if(${QT_MOBILITY_MAJOR_VERSION} EQUAL 1 AND ${QT_MOBILITY_MINOR_VERSION} LESS 1)
    set(Contacts_11_SRC )
else()
    set(Contacts_11_SRC
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactaction_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactactiondescriptor_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactactionfactory_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactactionfilter_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactactiontarget_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfavorite_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfetchbyidrequest_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontacthobby_wrapper.cpp
    ${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactmanagerenginev2_wrapper.cpp
    ${Contacts_12_SRC}
    )
endif()

set(Contacts_SRC
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/contacts_module_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactabstractrequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactaddress_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactanniversary_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactavatar_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactbirthday_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactchangelogfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactchangeset_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetaildefinitionfetchrequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetaildefinitionremoverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetaildefinitionsaverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetaildefinition_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetailfielddefinition_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetailfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetailrangefilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdetail_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactdisplaylabel_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactemailaddress_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfamily_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfetchhint_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfetchrequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactgender_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactgeolocation_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactglobalpresence_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactguid_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactid_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactintersectionfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactinvalidfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactlocalidfetchrequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactlocalidfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactmanagerenginefactory_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactmanagerengine_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactmanager_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactname_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactnickname_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactnote_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactonlineaccount_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactorganization_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactphonenumber_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactpresence_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactrelationshipfetchrequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactrelationshipfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactrelationshipremoverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactrelationshipsaverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactrelationship_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactremoverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactringtone_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactsaverequest_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactsortorder_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactsynctarget_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontacttag_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactthumbnail_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontacttimestamp_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontacttype_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontactunionfilter_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontacturl_wrapper.cpp
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts/qtmobility_qcontact_wrapper.cpp
${Contacts_11_SRC}
)

set(Contacts_INCLUDE_DIRECTORIES
${CMAKE_CURRENT_BINARY_DIR}/${BINDING_NAME}/Contacts
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
)

set(Contacts_LINK_LIBRARIES
${PYTHON_LIBRARIES}
${SHIBOKEN_LIBRARY}
${PYSIDE_LIBRARY}
${QT_QTCORE_LIBRARY}
${QT_MOBILITY_CONTACTS_LIBRARY}
)

CREATE_PYSIDE_MODULE(Contacts
                     ${QT_MOBILITY_CONTACTS_INCLUDE_DIR}
                     Contacts_SRC
                     Contacts_INCLUDE_DIRECTORIES
                     Contacts_LINK_LIBRARIES)



