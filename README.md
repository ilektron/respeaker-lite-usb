# respeaker-lite-usb
Attempts at developing custom firmware for the reSpeaker Lite to enable some of the additional features over USB

## What needs to be done in order to write a custom firware

Most of this is based on [this thread](https://forum.seeedstudio.com/t/inquiry-regarding-respeaker-lite-voice-assistant-kit/294711/4) for where to start and things that need to be figured out

Starting with an eval board example, 

### The changes when compared to a reSpeaker Lite

- Modify the board support config
- Adjust mic channel assignments
- Verify clock source assumptions
- Possibly tune FIR/AEC stages

## Tools and References

### Getting Development Started

[Quickstart Guide for XMOS](https://www.xmos.com/download/xcore_ai-Evaluation-Kit-Quick-Start%286%29.pdf/)

### Disassembler

- [xobjdump](https://www.xmos.com/download/app_disassembling_a_program_example-README%281_1_1rc0_a%29.pdf/)
 
In order to disassemble the binaries, you need to provide the `--march xs3a` flag because the xobjdump defaults to pulling architecture data from a `.xe` file which includes a lot more debug information than just the binary firmware

For example
```console
$ xobjdump  -d --march xs3a  respeaker_lite_usb_dfu_firmware_v2.0.7.bin
```


### Datasheets

- [XU316 Datasheet](https://www.xmos.com/download/XU316-1024-xcore_ai-Datasheet(2_0_0).pdf/?ws_referrer_origin=https%3A%2F%2Fwww.google.com%2F)
- [XS3 Architecture](https://www.xmos.com/download/The-XMOS-XS3-Architecture.pdf/)

### Reference Design

- [sw_usb_audio](https://www.xmos.com/documentation/XM-008854-UG/html/doc/rst/sw_usb_audio.html)

### Schematics

### Firmwares
