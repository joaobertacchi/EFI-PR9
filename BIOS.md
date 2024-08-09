# Description
This file contains the required BIOS config. Reset first to default settings!

# BIOS menus

## Advanced
- Advanced -> Wake on LAN => Disabled
- Advanced -> NCT5532D Super IO Configuration -> Serial Port 1 Configuration -> Serial Port => Disabled
- Advanced -> PIC Subsystem Settings -> Above 4G Decoding => Enabled
- Advanced -> PIC Subsystem Settings -> Re-Size BAR Support => Enabled
- Advanced -> CSM Configuration -> CSM Support => Disabled
- Advanced -> USB Configuration -> XHCI Hand-off => Enabled
- Advanced -> USB Configuration -> EHCI Hand-off => Enabled

## IntelRCSetup
- IntelRCSetup -> Processor Configuration -> MSR Lock Control => Disabled
- IntelRCSetup -> Common RefCode Configuration -> MMIOHBase => 1T
- IntelRCSetup -> Common RefCode Configuration -> MMIO High Size => 256G
IntelRCSetup -> Memory Configuration -> Memory Timings & Voltage Override -> DIMM profile => MANUAL
- IntelRCSetup -> Memory Configuration -> Memory Timings & Voltage Override -> Command Timing => 1N

## Boot
- Boot -> Setup Prompt Timeout => 1
- Boot -> Bootup NumLock State => Off (inverted config?)
- Boot -> Quiet Boot => Disabled

# Troubleshooting

## Computer don't boot (stuck before/during POST)
Clear CMOS and start apply BIOS configs from scratch. That happens when using Resizeble BAR with an incorrect config.plist setting.

## Opencore entry does not show up in BIOS
Leave only Opencore files in EFI partition (move Microsoft to a temporary one). You should be able to boot after that, and you can restore previous EFI (move Microsoft back in).
