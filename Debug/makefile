################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include system/src/newlib/subdir.mk
-include system/src/diag/subdir.mk
-include system/src/cortexm/subdir.mk
-include system/src/cmsis/subdir.mk
-include system/src/W7500x/subdir.mk
-include src/ioLibrary_Driver/MDIO/subdir.mk
-include src/ioLibrary_Driver/Internet/DNS/subdir.mk
-include src/ioLibrary_Driver/Internet/DHCP/subdir.mk
-include src/ioLibrary_Driver/Ethernet/W5500/subdir.mk
-include src/ioLibrary_Driver/Ethernet/W5300/subdir.mk
-include src/ioLibrary_Driver/Ethernet/W5200/subdir.mk
-include src/ioLibrary_Driver/Ethernet/W5100S/subdir.mk
-include src/ioLibrary_Driver/Ethernet/W5100/subdir.mk
-include src/ioLibrary_Driver/Ethernet/subdir.mk
-include src/ioLibrary_Driver/Application/loopback/subdir.mk
-include src/Serial_to_Ethernet2/subdir.mk
-include src/PlatformHandler/subdir.mk
-include src/Configuration/subdir.mk
-include src/Callback/subdir.mk
-include src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(CC_DEPS)),)
-include $(CC_DEPS)
endif
ifneq ($(strip $(C++_DEPS)),)
-include $(C++_DEPS)
endif
ifneq ($(strip $(C_UPPER_DEPS)),)
-include $(C_UPPER_DEPS)
endif
ifneq ($(strip $(CXX_DEPS)),)
-include $(CXX_DEPS)
endif
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(CPP_DEPS)),)
-include $(CPP_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
WIZ750SR_App.bin \

SECONDARY_SIZE += \
WIZ750SR_App.siz \


# All Target
all: WIZ750SR_App.elf secondary-outputs

# Tool invocations
WIZ750SR_App.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: Cross ARM C++ Linker'
	arm-none-eabi-g++ -mcpu=cortex-m0 -mthumb -Og -fmessage-length=0 -fsigned-char -ffunction-sections -fdata-sections -Wall -Wextra  -g3 -T mem.ld -T libs.ld -T sections.ld -nostartfiles -Xlinker --gc-sections -L"../ldscripts" -Wl,-Map,"WIZ750SR_App.map" --specs=nano.specs -o "WIZ750SR_App.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '
	$(MAKE) --no-print-directory post-build

WIZ750SR_App.bin: WIZ750SR_App.elf
	@echo 'Invoking: Cross ARM GNU Create Flash Image'
	arm-none-eabi-objcopy -O binary "WIZ750SR_App.elf"  "WIZ750SR_App.bin"
	@echo 'Finished building: $@'
	@echo ' '

WIZ750SR_App.siz: WIZ750SR_App.elf
	@echo 'Invoking: Cross ARM GNU Print Size'
	arm-none-eabi-size --format=berkeley "WIZ750SR_App.elf"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(CC_DEPS)$(C++_DEPS)$(OBJS)$(C_UPPER_DEPS)$(CXX_DEPS)$(SECONDARY_FLASH)$(SECONDARY_SIZE)$(ASM_DEPS)$(S_UPPER_DEPS)$(C_DEPS)$(CPP_DEPS) WIZ750SR_App.elf
	-@echo ' '

post-build:
	-arm-none-eabi-objcopy -O ihex "WIZ750SR_App.elf" "WIZ750SR_App.hex";arm-none-eabi-objcopy -O srec "WIZ750SR_App.elf" "WIZ750SR_App.srec"
	-@echo ' '

secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_SIZE)

.PHONY: all clean dependents post-build

-include ../makefile.targets
