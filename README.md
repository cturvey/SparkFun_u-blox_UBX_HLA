
# u-blox UBX Analyzer
  
A Logic2 High Level Analyzer for the u-blox UBX protocol. Also supports NMEA and RTCM.

![Screen shot 1](./img/Screenshot_1.png)

![Screen shot 2](./img/Screenshot_2.png)

![Screen shot 3](./img/Screenshot_3.png)

![Screen shot 4 SPI](./img/Screenshot_4.png)

Written for the [Saleae Logic Pro 8 USB Logic Analyzer](https://www.sparkfun.com/products/13196):

[![Saleae Logic Pro 8 USB Logic Analyzer](https://cdn.sparkfun.com//assets/parts/1/0/3/3/0/13196-04.jpg)](https://www.sparkfun.com/products/13196)

## v1.0.2

* NMEA decoding (format and checksum only).
* RTCM decoding (length, type and checksum only).
* Add SPI support:
  * Channel can be selected as miso or mosi.
  * You can add two instances of the analyzer to monitor both channels simultaneously.
* Add NAV-POSECEF and NAV-POSLLH.
* Add M8 vs. M6 module selection.

Contributed by [@maehw](https://github.com/maehw) :

* Add support for decoding CFG-PRT, CFG-RST, CFG-MSG, MON-VER, MON-HW, NAV-STATUS and NAV-TIMEGPS messages.
  * Includes support for u-blox 6 and u-blox 8 Protocol Specifications.

## v1.0.1

* Add support for NEO-D9S: decode UBX-RXM-PMP (Versions 0 and 1); UBX-INF-NOTICE, -ERROR and -WARNING.

## v1.0.0

* Proof of concept for Async Serial (UART) and I2C traffic: demonstrates that the HLA can successfully decode UBX frames when interleaved with NMEA messages.
* Provides simple decoding of UBX frames: displays the frame class, ID, length; extracts UBX-ACK-ACK, UBX-ACK-NACK and UBX-NAV-PVT fields; validates the checksum bytes.

## Upgrade Path

* Add decoding of more message types.
* Add proper support for the u-blox register layout and read transfers. Currently if the number of bytes in the I2C buffer is 0x62B5, the analyzer will attempt to decode that as a packet.
* Use ```I2C_ADDRESS_SETTING``` to filter messages on the selected I2C Address.

## Contributing

Thank you so *much* for offering to help out. We truly appreciate it.

If you'd like to contribute, start by searching through the [issues](https://github.com/sparkfun/SparkFun_u-blox_UBX_HLA/issues) and [pull requests](https://github.com/sparkfun/SparkFun_u-blox_UBX_HLA/pulls) to see whether someone else has raised a similar idea or question.
Please check the [closed issues](https://github.com/sparkfun/SparkFun_u-blox_UBX_HLA/issues?q=is%3Aissue+is%3Aclosed)
and [closed pull requests](https://github.com/sparkfun/SparkFun_u-blox_UBX_HLA/pulls?q=is%3Apr+is%3Aclosed) too - you may find that your issue or feature has already been discussed.

If you decide to add a feature to this analyzer, please create a Pull Request and follow these best practices:

* Change as little as possible. Do not submit a PR that changes 100 lines of whitespace. Break it up into multiple PRs if necessary.
* **Important:** Please submit your PR using the [release_candidate branch](https://github.com/sparkfun/SparkFun_u-blox_UBX_HLA/tree/release_candidate). That way, we can merge and test your PR quickly without changing the _main_ branch

## License

License: MIT. Please see [LICENSE.md](./LICENSE.md) for more details.