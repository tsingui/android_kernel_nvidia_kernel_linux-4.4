#
# Makefile for NVS (NVidia Sensor framework).
#
obj-$(CONFIG_NVS) += nvs.o

nvs-objs :=	nvs_vreg.o nvs_of_dt.o nvs_timestamp.o nvs_dsm.o \
		nvs_auto.o

ifneq (,$(filter $(CONFIG_NVS_LIGHT),y m))
nvs-objs += nvs_light.o
endif

ifneq (,$(filter $(CONFIG_NVS_PROXIMITY),y m))
nvs-objs += nvs_proximity.o
endif

ifneq (,$(filter $(CONFIG_NVS_IIO),y m))
nvs-objs += nvs_iio.o
CFLAGS_nvs_dsm.o += -DNVS_KIF_IIO=1
CFLAGS_nvs_auto.o += -DNVS_KIF_IIO=1
endif

ifneq (,$(filter $(CONFIG_NVS_RELAY),y m))
nvs-objs += nvs_relay.o nvs_sysfs.o
CFLAGS_nvs_dsm.o += -DNVS_KIF_RELAY=1
CFLAGS_nvs_auto.o += -DNVS_KIF_RELAY=1
endif

ifneq (,$(filter $(CONFIG_NVS_INPUT),y m))

nvs-objs += nvs_input.o nvs_sysfs.o
CFLAGS_nvs_dsm.o += -DNVS_KIF_INPUT=1
CFLAGS_nvs_auto.o += -DNVS_KIF_INPUT=1
endif
