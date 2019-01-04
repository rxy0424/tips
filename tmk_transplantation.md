# TMK Transplantation
## bootloader.c
### void bootloader_jump(void)
jump to bootloader when this function is called.

## eeconfig.c
### bool eeconfig_is_enabled(void)
return wetherater the eeprom config is enabled
### void eeconfig_init(void)
init eeprom config
### void eeconfig_enable(void)
enable eepprom config
### void eeconfig_disable(void)
disable eeprom config
### uint8_t eeconfig_read_debug(void)
return debug config saved in eeprom
### void eeconfig_write_debug(uint8_t val);
write debug config to eeprom
### uint8_t eeconfig_read_default_layer(void)
return defalut layer saved in eeprom
### void eeconfig_write_default_layer(uint8_t val)
write default layer to eeprom
### uint8_t eeconfig_read_keymap(void)
read keymap from eeprom
### void eeconfig_write_keymap(uint8_t val)
write keymap to eeprom
### uint8_t eeconfig_read_backlight(void)
read backlight config from eeprom
### void eeconfig_write_backlight(uint8_t val)
write backlight config to eeprom

## sleep_led.c
### void sleep_led_init(void)
init sleep led
### sleep_led_enable(void)
enable sleep led
### void sleep_led_disable(void)
disable sleep led
### void sleep_led_on(void)
make sleep led on
### void sleep_led_off(void)
make sleep led off

## suart.s(used in int main(void))
### void xmit(uint8_t data)
transmit a byte in serial format of N81
### uint8_t rcvr(void)
receive a byte
### uint8_t recv(void)

## common/common.h(xprintf.h)
### print(s)
### println(s)

## common/sendchar.h


## xprintf.h

## suspend.c
### void suspend_idle(uint8_t timeout)
unknown

### void suspend_power_down(void)
### bool suspend_wakeup_condition(void)
return true if need to wakeup
### void suspend_wakeup_init()

## timer.c

### void timer_int(void)
### timer_clear(void)
### uint16_t timer_read(void)
### uint32_t timer_read32(void)
### uint16_t timer_elapsed(uint16_t last)
### uint32_t timer_elapsed32(uint32_t last)