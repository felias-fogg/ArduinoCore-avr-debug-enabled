# Arduino AVR Boards (Debug enabled)

[![Check Arduino status](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/check-arduino.yml/badge.svg)](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/check-arduino.yml)
[![Compile Examples status](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/compile-platform-examples.yml/badge.svg)](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/compile-platform-examples.yml)
[![Spell Check status](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/spell-check.yml/badge.svg)](https://github.com/felias-fogg/ArduinoCore-avr-debug-enabled/actions/workflows/spell-check.yml)

This is a fork of the repository that contains the source code and configuration files of the Arduino AVR Boards [platform](https://arduino.github.io/arduino-cli/latest/platform-specification/). It contains the changes to allow for debugging of the classic AVR MCUs in the Arduino IDE 2. Specifically, there are the following changes:

- `platform.txt` contains changes to make it possible to invoke the GDB server PyAvrOCD.
- `boards.txt` contains changes to allow for enabling JTAG debugging and for disabling link time optimization (LTO). In addition, the lock bits are now all specified according to the data sheets (all unused bits are '1').
- `programmers.txt` contains additional programmers and allows for JTAG programming mode. 

- The newer avrdude version (8.0) is employed, so that Atmel-ICE can set lock bits.

You can install this fork by adding the following 'Additional Board manager URL' in the preference dialog: 

```
https://felias-fogg.github.io/packages_debugging_index.json
```

Then choose 'Arduino AVR Boards (Debug enabled)' in the `Board Manager`. After it, you can remove the official 'Arduino AVR Boards'.

For help concerning debugging, consult the [PyAvrOCD manual](https://felias-fogg.github.io/PyAvrOCD/).

This fork is based on version 1.8.6. It has its own version numbering scheme, though, since the debugging part will probably evolve over time. Changes from the upstream repo will be added in a timely fashion. The chances of integrating this fork into the official distribution are probably not very high.
