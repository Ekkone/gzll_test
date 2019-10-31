PROJECT_NAME     := gzll_ack_payload_device_pca10040
TARGETS          := nrf52832_xxaa
OUTPUT_DIRECTORY := _build

SDK_ROOT := ../../../nRF5_SDK_15.3.0_59ac345/
PROJ_DIR := ..

$(OUTPUT_DIRECTORY)/nrf52832_xxaa.out: \
  LINKER_SCRIPT  := gzll_ack_payload_device_gcc_nrf52.ld

# Source files common to all targets
SRC_FILES += \
	$(PROJ_DIR)/main.c \
	$(PROJ_DIR)/BSP/oled.c \
	$(PROJ_DIR)/BSP/beep.c \
	$(PROJ_DIR)/BSP/led.c \
	$(PROJ_DIR)/BSP/key.c \
	$(PROJ_DIR)/Start/gcc_startup_nrf52.S \
	$(PROJ_DIR)/Start/system_nrf52.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_backend_rtt.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_backend_serial.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_backend_uart.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_default_backends.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_frontend.c \
	$(PROJ_DIR)/nRF_Log/nrf_log_str_formatter.c \
	$(PROJ_DIR)/BoardDefinition/boards.c \
	$(PROJ_DIR)/nRF_Libraries/app_button.c \
	$(PROJ_DIR)/nRF_Libraries/app_error.c \
	$(PROJ_DIR)/nRF_Libraries/app_error_handler_gcc.c \
	$(PROJ_DIR)/nRF_Libraries/app_error_weak.c \
	$(PROJ_DIR)/nRF_Libraries/app_scheduler.c \
	$(PROJ_DIR)/nRF_Libraries/app_timer.c \
	$(PROJ_DIR)/nRF_Libraries/app_util_platform.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_assert.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_atomic.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_balloc.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_fprintf.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_fprintf_format.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_memobj.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_ringbuf.c \
	$(PROJ_DIR)/nRF_Libraries/nrf_strerror.c \
	$(PROJ_DIR)/nRF_Drivers/nrf_drv_uart.c \
	$(PROJ_DIR)/nRF_Drivers/nrfx_atomic.c \
	$(PROJ_DIR)/nRF_Drivers/nrfx_gpiote.c \
	$(PROJ_DIR)/nRF_Drivers/nrfx_prs.c \
	$(PROJ_DIR)/nRF_Drivers/nrfx_uart.c \
	$(PROJ_DIR)/nRF_Drivers/nrfx_uarte.c \
	$(PROJ_DIR)/BoardSupport/bsp.c \
	$(PROJ_DIR)/nRF_Segger_RTT/SEGGER_RTT.c \
	$(PROJ_DIR)/nRF_Segger_RTT/SEGGER_RTT_Syscalls_GCC.c \
	$(PROJ_DIR)/nRF_Segger_RTT/SEGGER_RTT_printf.c \


# Include folders common to all targets
INC_FOLDERS += \
	$(PROJ_DIR)/BSP/ \
	$(SDK_ROOT)/components/proprietary_rf/gzll \
	$(SDK_ROOT)/integration/nrfx \
	$(PROJ_DIR) \
	$(SDK_ROOT)/components/libraries/scheduler \
	../config \
	$(SDK_ROOT)/components/libraries/experimental_section_vars \
	$(SDK_ROOT)/modules/nrfx/mdk \
	$(SDK_ROOT)/components/libraries/strerror \
	$(SDK_ROOT)/components/boards \
	$(SDK_ROOT)/components/drivers_nrf/nrf_soc_nosd \
	$(SDK_ROOT)/components/libraries/button \
	$(SDK_ROOT)/components/libraries/log \
	$(SDK_ROOT)/modules/nrfx/hal \
	$(SDK_ROOT)/components/libraries/log/src \
	$(SDK_ROOT)/components/libraries/bsp \
	$(SDK_ROOT)/integration/nrfx/legacy \
	$(SDK_ROOT)/modules/nrfx/drivers/include \
	$(SDK_ROOT)/components/libraries/ringbuf \
	$(SDK_ROOT)/external/fprintf \
	$(SDK_ROOT)/components/libraries/balloc \
	$(SDK_ROOT)/components/libraries/util \
	$(SDK_ROOT)/modules/nrfx \
	$(SDK_ROOT)/modules/nrfx/soc \
	$(SDK_ROOT)/modules/nrfx/drivers/src/prs\
	$(SDK_ROOT)/components \
	$(SDK_ROOT)/external/segger_rtt \
	$(SDK_ROOT)/components/libraries/memobj \
	$(SDK_ROOT)/components/libraries/atomic \
	$(SDK_ROOT)/components/libraries/delay \
	$(SDK_ROOT)/components/toolchain/cmsis/include \
	$(SDK_ROOT)/components/libraries/timer \

# Libraries common to all targets
LIB_FILES += \
  $(SDK_ROOT)/components/proprietary_rf/gzll/gcc/gzll_nrf52_sd_resources_gcc.a \

# Optimization flags
OPT = -O3 -g3
# Uncomment the line below to enable link time optimization
#OPT += -flto

# C flags common to all targets
CFLAGS += $(OPT)
CFLAGS += -DBOARD_CUSTOM
CFLAGS += -DCONFIG_GPIO_AS_PINRESET
CFLAGS += -DFLOAT_ABI_HARD
CFLAGS += -DGAZELL_ALTERNATIVE_RESOURCES
CFLAGS += -DGAZELL_PRESENT
CFLAGS += -DNRF52
CFLAGS += -DNRF52832_XXAA
CFLAGS += -DNRF52_PAN_74
CFLAGS += -DSWI_DISABLE0
CFLAGS += -DUSE_SD_HW_RESOURCES
CFLAGS += -mcpu=cortex-m4
CFLAGS += -mthumb -mabi=aapcs
CFLAGS += -Wall #-Werror
CFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
# keep every function in a separate section, this allows linker to discard unused ones
CFLAGS += -ffunction-sections -fdata-sections -fno-strict-aliasing
CFLAGS += -fno-builtin -fshort-enums

# C++ flags common to all targets
CXXFLAGS += $(OPT)

# Assembler flags common to all targets
ASMFLAGS += -g3
ASMFLAGS += -mcpu=cortex-m4
ASMFLAGS += -mthumb -mabi=aapcs
ASMFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
ASMFLAGS += -DBOARD_PCA10040
ASMFLAGS += -DCONFIG_GPIO_AS_PINRESET
ASMFLAGS += -DFLOAT_ABI_HARD
ASMFLAGS += -DGAZELL_ALTERNATIVE_RESOURCES
ASMFLAGS += -DGAZELL_PRESENT
ASMFLAGS += -DNRF52
ASMFLAGS += -DNRF52832_XXAA
ASMFLAGS += -DNRF52_PAN_74
ASMFLAGS += -DSWI_DISABLE0
ASMFLAGS += -DUSE_SD_HW_RESOURCES

# Linker flags
LDFLAGS += $(OPT)
LDFLAGS += -mthumb -mabi=aapcs -L$(SDK_ROOT)/modules/nrfx/mdk -T$(LINKER_SCRIPT)
LDFLAGS += -mcpu=cortex-m4
LDFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
# let linker dump unused sections
LDFLAGS += -Wl,--gc-sections
# use newlib in nano version
LDFLAGS += --specs=nano.specs

nrf52832_xxaa: CFLAGS += -D__HEAP_SIZE=8192
nrf52832_xxaa: CFLAGS += -D__STACK_SIZE=8192
nrf52832_xxaa: ASMFLAGS += -D__HEAP_SIZE=8192
nrf52832_xxaa: ASMFLAGS += -D__STACK_SIZE=8192

# Add standard libraries at the very end of the linker input, after all objects
# that may need symbols provided by these libraries.
LIB_FILES += -lc -lnosys -lm


.PHONY: default help

# Default target - first one defined
default: nrf52832_xxaa

# Print all targets that can be built
help:
	@echo following targets are available:
	@echo		nrf52832_xxaa
	@echo		sdk_config - starting external tool for editing sdk_config.h
	@echo		flash      - flashing binary

TEMPLATE_PATH := $(SDK_ROOT)/components/toolchain/gcc


include $(TEMPLATE_PATH)/Makefile.common

$(foreach target, $(TARGETS), $(call define_target, $(target)))

.PHONY: flash erase

# Flash the program
flash: default
	@echo Flashing: $(OUTPUT_DIRECTORY)/nrf52832_xxaa.hex
	nrfjprog -f nrf52 --program $(OUTPUT_DIRECTORY)/nrf52832_xxaa.hex --sectorerase
	nrfjprog -f nrf52 --reset

erase:
	nrfjprog -f nrf52 --eraseall

SDK_CONFIG_FILE := ../config/sdk_config.h
CMSIS_CONFIG_TOOL := $(SDK_ROOT)/external_tools/cmsisconfig/CMSIS_Configuration_Wizard.jar
sdk_config:
	java -jar $(CMSIS_CONFIG_TOOL) $(SDK_CONFIG_FILE)
