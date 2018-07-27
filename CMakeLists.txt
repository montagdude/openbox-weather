cmake_minimum_required(VERSION 2.8.8)
project(openbox-weather NONE)
set(OPENBOX_WEATHER_VERSION 0.1)

# Some default directories
set(CONFDIR /etc/openbox-weather
    CACHE PATH "Directory to install config.py")
set(DATADIR ${CMAKE_INSTALL_PREFIX}/share/openbox-weather
    CACHE PATH "Directory to install shared data")

configure_file(openbox-weather.in openbox-weather)
configure_file(config.py.in config.py)

install(FILES ${CMAKE_BINARY_DIR}/openbox-weather
        PERMISSIONS OWNER_READ OWNER_WRITE OWNER_EXECUTE
                    GROUP_READ             GROUP_EXECUTE
                    WORLD_READ             WORLD_EXECUTE
        DESTINATION bin)
install(FILES ${CMAKE_BINARY_DIR}/config.py DESTINATION ${CONFDIR})
install(DIRECTORY icons DESTINATION ${DATADIR})

