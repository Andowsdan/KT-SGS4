GCC_VERSION      := $(shell $(CONFIG_SHELL) $(PWD)/scripts/gcc-version.sh $(CROSS_COMPILE)gcc)
ccflags-y += -Idrivers/media/video/msm
ccflags-y += -Idrivers/media/video/msm/server
ifeq ($(CONFIG_MACH_JACTIVE_EUR),y)
ccflags-y += -Idrivers/video/msm
endif
ifeq ($(CONFIG_MACH_JACTIVE_ATT),y)
ccflags-y += -Idrivers/video/msm
endif
ifeq ($(GCC_VERSION),0404)
CFLAGS_REMOVE_msm_vfe8x.o = -Wframe-larger-than=1024
endif
ifeq ($(CONFIG_MSM_CAMERA_V4L2),y)
  obj-$(CONFIG_ARCH_MSM7X27A) += msm_vfe7x27a_v4l2.o
  obj-$(CONFIG_ARCH_MSM8X60) += msm_vfe31_v4l2.o
  obj-$(CONFIG_ARCH_MSM7X30) += msm_vfe31_v4l2.o
else
  obj-$(CONFIG_ARCH_MSM7X27A) += msm_vfe7x27a.o
  obj-$(CONFIG_ARCH_MSM8X60) += msm_vfe31.o
  obj-$(CONFIG_ARCH_MSM7X30) += msm_vfe31.o
endif
obj-$(CONFIG_ARCH_MSM_ARM11) += msm_vfe7x.o
obj-$(CONFIG_ARCH_QSD8X50) += msm_vfe8x.o msm_vfe8x_proc.o

obj-$(CONFIG_ARCH_MSM8960) += msm_vfe32.o
ifeq ($(CONFIG_MACH_JACTIVE_EUR),y)
obj-$(CONFIG_ARCH_MSM8960) += msm_vfe32-jfactive.o
else
ifeq ($(CONFIG_MACH_JACTIVE_ATT),y)
obj-$(CONFIG_ARCH_MSM8960) += msm_vfe32-jfactive.o
else
obj-$(CONFIG_ARCH_MSM8960) += msm_vfe32.o
endif
endif

obj-$(CONFIG_ARCH_MSM8974) += msm_vfe40.o
obj-$(CONFIG_MSM_CAMERA_V4L2) += msm_vfe_stats_buf.o
