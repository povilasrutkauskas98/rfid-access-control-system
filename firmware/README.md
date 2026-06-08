## Firmware Development

The firmware was developed in **C** using **Keil μVision**, while the microcontroller configuration and peripheral initialization code were generated using **STM32CubeMX**. Programming and debugging were performed through the **ST-Link** interface using the **Serial Wire Debug (SWD)** protocol.

### Microcontroller Configuration

The STM32F407VG microcontroller was configured to operate at its maximum clock frequency of **168 MHz** using an external crystal oscillator.

The following peripherals were used:

* SPI1 – communication with the ST25R3911 RFID reader
* SPI2 – communication with the ENC28J60 Ethernet controller
* USART1 – debugging and diagnostic output
* USART2 – serial communication and system monitoring
* External interrupts for RFID reader event handling

SPI communication frequencies were configured according to the manufacturers' recommendations:

* ENC28J60 Ethernet controller: 10 MHz SPI clock
* ST25R3911 RFID reader: 4.5 MHz SPI clock
<img width="780" height="792" alt="image" src="https://github.com/user-attachments/assets/4b82823a-8a1e-40f5-a616-b0f72d2cbdce" />


### Firmware Features

The firmware performs the following tasks:

1. Initializes the STM32F407VG microcontroller and peripherals.
2. Configures the Ethernet interface and network parameters.
3. Initializes the ST25R3911 RFID reader.
4. Continuously scans for RFID/NFC cards.
5. Reads the card UID using the ISO15693 protocol.
6. Matches the detected UID with registered users.
7. Sends access event information to the embedded web interface.
8. Provides diagnostic information through UART debugging channels.

### Development Tools

* Programming Language: C
* IDE: Keil μVision
* MCU Configuration: STM32CubeMX
* Debugger: ST-Link
* Debug Interface: SWD (Serial Wire Debug)

