## Embedded Web Interface

To enable network communication, the STM32F407VG microcontroller was configured with a static IP address and connected to the local Ethernet network through the ENC28J60 controller.

Before implementing the web interface, basic network connectivity was verified using ICMP echo requests (ping). Successful responses confirmed proper Ethernet communication between the microcontroller and the host computer.

Network traffic was monitored using Wireshark, where ICMP request and reply packets were captured and analyzed. This verified that the embedded device was correctly receiving and responding to network requests.

### Web Server Implementation

After validating Ethernet communication, a lightweight embedded HTTP server was implemented on the STM32 microcontroller.

The web page content was initially created as an `index.html` file and then converted into a byte array using the `makefsdata` utility. The generated data was stored in the microcontroller Flash memory and served to clients through HTTP requests.

When a user enters the device IP address in a web browser, the microcontroller responds with the stored HTML page displaying access control information.

### Access Event Visualization

The firmware continuously monitors RFID card activity through the ST25R3911 reader. When a valid card is detected, the card UID is matched against a predefined user database. The corresponding user information is then dynamically inserted into the web page, allowing access events to be viewed through a standard web browser.

### Features

* Embedded HTTP server running on STM32F407VG
* ENC28J60 Ethernet communication
* ICMP connectivity verification
* Static IP network configuration
* HTML page stored in Flash memory
* Real-time RFID user identification display
* Browser-based access control monitoring


## Network Communication Test

<img width="989" height="309" alt="image" src="https://github.com/user-attachments/assets/c57e06c5-7b36-40eb-854b-9e1c5717d9a8" />


Successful ICMP communication between the host PC and the STM32 device.

## Wireshark Capture

<img width="1028" height="281" alt="image" src="https://github.com/user-attachments/assets/ab562d5f-570d-4b11-ae70-b8fd7265543f" />

Captured ICMP request and reply packets.

## HTML Source
<img width="802" height="227" alt="image" src="https://github.com/user-attachments/assets/90b1e861-943d-4330-97ac-36644351a4e8" />


Embedded web page source used by the HTTP server.

## Web Interface

<img width="889" height="285" alt="image" src="https://github.com/user-attachments/assets/be417db1-d89b-4f36-a4ee-dd25644509a9" />
<img width="602" height="278" alt="image" src="https://github.com/user-attachments/assets/3c5cb0ca-28ca-4a01-9dcc-ac63d00259f5" />


Access control information displayed in a web browser.
