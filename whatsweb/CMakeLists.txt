cmake_minimum_required(VERSION 3.5)
project(whatsweb C CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

#Notification module
add_subdirectory(qml-notify-module)

# Install QML APP
install(DIRECTORY app/ DESTINATION ${CMAKE_INSTALL_PREFIX}/app/)

# Install main project files
install(FILES whatsweb.apparmor DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES whatsweb.desktop DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES manifest.json DESTINATION ${CMAKE_INSTALL_PREFIX})

#Icon
install(FILES icon.png DESTINATION ${CMAKE_INSTALL_PREFIX})

#SPECIFIC FILES FOR NOTIFICATIONS
install(PROGRAMS pushexec DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES whatsweb-push-helper.json DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES whatsweb-push.apparmor DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES push-apparmor.json DESTINATION ${CMAKE_INSTALL_PREFIX})

#OTHER FILES
install(FILES content-hub.json DESTINATION ${CMAKE_INSTALL_PREFIX})
install(FILES icon-splash.png DESTINATION ${CMAKE_INSTALL_PREFIX})
