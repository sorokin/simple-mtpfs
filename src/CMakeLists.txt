add_executable(simple-mtpfs
    ./simple-mtpfs-fuse.cpp
    ./simple-mtpfs-libmtp.cpp
    ./simple-mtpfs-log.cpp
    ./simple-mtpfs-main.cpp
    ./simple-mtpfs-mtp-device.cpp
    ./simple-mtpfs-sha1.cpp
    ./simple-mtpfs-tmp-files-pool.cpp
    ./simple-mtpfs-type-dir.cpp
    ./simple-mtpfs-type-file.cpp
    ./simple-mtpfs-type-tmp-file.cpp
    ./simple-mtpfs-util.cpp)

target_link_libraries(simple-mtpfs mtp fuse)

install(TARGETS simple-mtpfs DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)
