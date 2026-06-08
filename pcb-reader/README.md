### RFID Reader

The RFID reader is based on the **ST25R3911** NFC/RFID reader IC, selected for compatibility with the **ST25TV** identification tag used in this project. The device supports the **ISO15693** protocol, making it well suited for reliable communication with passive RFID cards operating at **13.56 MHz**.

The ST25R3911 provides low power consumption, high receiver sensitivity, and fast data exchange capabilities. These features enable reliable card detection and identification while maintaining efficient system operation.

The reader communicates with the STM32F407VG microcontroller via the SPI interface, where card identifiers are processed and forwarded to the Ethernet module for transmission to the web-based access control system.

<img width="303" height="436" alt="image" src="https://github.com/user-attachments/assets/0b24e858-4851-44bd-bc3f-f3d12b36b54e" />

<img width="323" height="444" alt="image" src="https://github.com/user-attachments/assets/39ca8aa7-51dd-4f2f-82f6-93dc7e648e78" />


