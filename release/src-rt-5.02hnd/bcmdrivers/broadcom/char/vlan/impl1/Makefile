# File: bcmdrivers/char/vlan/bcm963xx/Makefile
#
# Makefile for the BCM68xx VLAN driver.
#

obj-$(CONFIG_BCM_VLAN) += bcmvlan.o
ifneq ($(PREBUILT_EXTRAMOD),1)
bcmvlan-objs += bcm_vlan.o bcm_vlan_local.o bcm_vlan_user.o bcm_vlan_dev.o bcm_vlan_rule.o bcm_vlan_test.o bcm_vlan_flows.o
else
bcmvlan-objs := bcmvlan_preb.o
endif

EXTRA_CFLAGS += -I$(obj)
EXTRA_CFLAGS += -I$(INC_BRCMDRIVER_PUB_PATH)/$(BRCM_BOARD)
EXTRA_CFLAGS += -I$(INC_BRCMDRIVER_PRIV_PATH)/$(BRCM_BOARD)
EXTRA_CFLAGS += -I$(INC_BRCMBOARDPARMS_PATH)/$(BRCM_BOARD)
EXTRA_CFLAGS += -I$(INC_BRCMSHARED_PUB_PATH)/$(BRCM_BOARD)
EXTRA_CFLAGS += -I$(INC_BRCMSHARED_PRIV_PATH)/$(BRCM_BOARD)
EXTRA_CFLAGS += $(EXTRA_INCLUDES) $(INC_RDP_FLAGS)
EXTRA_CFLAGS += -Werror -Wall

-include $(TOPDIR)/Rules.make

clean:
	rm -f core *.o *.a *.s .*.cmd *.ko

#
# This target is to support builds of binary only vlan module
# in the customer builds.  This target is called from the
# kernel/linux/Makefile before MODPOST.
#
getrealobjects:
#       if [ -e vlan.impl2.tar.gz -a -e bcm_vlan.o ]; then \
#         echo "Restoring real vlan objects..."; \
#         tar -zxf vlan.impl2.tar.gz; \
#         touch bcm_vlan.o PPloamDS.o bcm_vlan_omci.o bcm_vlan_omci_usr.o; \
#         touch bcm_vlan_omci_proc.o bcm_vlan_fpga.o \
#         touch built-in.o; \
#         sleep 1; \
#         touch bcmvlan.o; \
#         touch bcmvlan.mod.o; \
#         touch bcmvlan.ko; \
#       fi

