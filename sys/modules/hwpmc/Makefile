#
# $FreeBSD$
#

.PATH: ${SRCTOP}/sys/dev/hwpmc

KMOD=	hwpmc

SRCS=	hwpmc_mod.c hwpmc_logging.c hwpmc_soft.c vnode_if.h

.if ${MACHINE_CPUARCH} == "aarch64"
SRCS+=  hwpmc_arm64.c hwpmc_arm64_md.c
.endif

.if ${MACHINE_CPUARCH} == "amd64"
SRCS+=	hwpmc_amd.c hwpmc_core.c hwpmc_intel.c hwpmc_piv.c hwpmc_tsc.c
SRCS+=	hwpmc_x86.c hwpmc_uncore.c
SRCS+=	device_if.h bus_if.h
.endif

.if ${MACHINE_CPUARCH} == "arm"
SRCS+=	hwpmc_arm.c
.endif

.if ${MACHINE_CPUARCH} == "i386"
SRCS+=	hwpmc_amd.c hwpmc_core.c hwpmc_intel.c hwpmc_piv.c hwpmc_ppro.c
SRCS+=	hwpmc_pentium.c hwpmc_tsc.c hwpmc_x86.c hwpmc_uncore.c
SRCS+=	device_if.h bus_if.h
.endif

.if ${MACHINE_CPUARCH} == "powerpc"
SRCS+=	hwpmc_powerpc.c hwpmc_e500.c hwpmc_mpc7xxx.c hwpmc_ppc970.c
.endif

.if ${MACHINE_CPUARCH} == "sparc64"
SRCS+=	hwpmc_sparc64.c
.endif

.include <bsd.kmod.mk>
