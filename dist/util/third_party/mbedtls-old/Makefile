MODULE = gecko_sdk_mbedtls


GECKO_SDK_SRCDIR = $(PKGDIRBASE)/gecko_sdk/dist

MBEDTLS_INCLUDES =
MBEDTLS_INCLUDES += -I$(GECKO_SDK_SRCDIR)/util/third_party/mbedtls/configs
MBEDTLS_INCLUDES += -I$(GECKO_SDK_SRCDIR)/util/third_party/mbedtls/include
MBEDTLS_INCLUDES += -I$(GECKO_SDK_SRCDIR)/util/third_party/mbedtls/include/mbedtls
MBEDTLS_INCLUDES += -I$(GECKO_SDK_SRCDIR)/util/third_party/mbedtls/sl_crypto/include

export INCLUDES += $(MBEDTLS_INCLUDES)


#DEVICE = ${CPU_MODEL}			# TODO
DEVICE = EFR32MG13P733F512GM48

CFLAGS += -D$(DEVICE) -DMBEDTLS_CONFIG_FILE='<config-sl-crypto-all-acceleration.h>'
CFLAGS += -Wno-old-style-definition -Wno-misleading-indentation


DIRS = library sl_crypto/src


include $(RIOTBASE)/Makefile.base
