libhirte_src = [
    'include/node.h',
    'include/orchestrator.h',
    'include/bus/peer-bus.h',
    'include/bus/user-bus.h',
    'include/bus/systemd-bus.h',
    'include/socket.h',
    'include/common/memory.h',
    'include/orchestrator/peer-manager.h',
    'include/service/service.h',
    'include/service/shutdown.h',

    'src/common/memory.h',
    'src/common/dbus.h',
    'src/node.c',
    'src/orchestrator.c',
    'src/bus/peer-bus.c',
    'src/bus/user-bus.c',
    'src/bus/systemd-bus.c',
    'src/socket.c',
    'src/orchestrator/peer-manager.c',
    'src/service/service.c',
    'src/service/shutdown.c',
]

# We use libtool-version numbers because it's easier to understand.
# Before making a release, the libruntime_so_*
# numbers should be modified. The components are of the form C:R:A.
# a) If binary compatibility has been broken (eg removed or changed interfaces)
#    change to C+1:0:0.
# b) If interfaces have been changed or added, but binary compatibility has
#    been preserved, change to C+1:0:A+1
# c) If the interface is the same as the previous version, change to C:R+1:A
libruntime_lt_c=1
libruntime_lt_r=0
libruntime_lt_a=0

libruntime_so_version = '@0@.@1@.@2@'.format((libruntime_lt_c - libruntime_lt_a),
                                              libruntime_lt_a,
                                              libruntime_lt_r)

hirte_lib = shared_library('hirte',
                            libhirte_src,
                            dependencies: [
                                systemd_dep
                            ],
                            version : libruntime_so_version,
                            install : true)


# build test binaries
subdir('test')
