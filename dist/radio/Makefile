MODULE = gecko_sdk_librail

RAIL_LIB_VERSION ?=1.1

RAIL_SDK_SRCDIR = $(PKGDIRBASE)/gecko_sdk/dist/radio/rail_lib_v$(RAIL_LIB_VERSION)

ifeq ($(EFM32_FAMILY),efr32mg1p)
	RAIL_LIB = $(RAIL_SDK_SRCDIR)/autogen/librail_release/librail_efr32xg1_gcc_release.a
endif
ifeq ($(EFM32_FAMILY),efr32mg12p)
	RAIL_LIB = $(RAIL_SDK_SRCDIR)/autogen/librail_release/librail_efr32xg12_gcc_release.a
endif
ifeq ($(EFM32_FAMILY),efr32mg13p)
	RAIL_LIB = $(RAIL_SDK_SRCDIR)/autogen/librail_release/librail_efr32xg13_gcc_release.a
endif

$(BINDIR)/$(MODULE).a:
	cp $(RAIL_LIB) $@
	arm-none-eabi-objcopy $@ \
		--redefine-sym FRC_PRI_IRQHandler=isr_frc_pri \
		--redefine-sym FRC_IRQHandler=isr_frc \
		--redefine-sym MODEM_IRQHandler=isr_modem \
		--redefine-sym RAC_SEQ_IRQHandler=isr_rac_seq \
		--redefine-sym RAC_RSM_IRQHandler=isr_rac_rsm \
		--redefine-sym BUFC_IRQHandler=isr_bufc \
		--redefine-sym AGC_IRQHandler=isr_agc \
		--redefine-sym PROTIMER_IRQHandler=isr_protimer \
		--redefine-sym SYNTH_IRQHandler=isr_synth \
		--redefine-sym RFSENSE_IRQHandler=isr_rfsense

