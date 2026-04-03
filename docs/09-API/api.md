---
title: Module's API
---

## Overview
This page lists all possible API calls that subsystem A3 can handle. Subsystem A3 acts as the onboard side of the bluetooth relay connecting the handheld controller to the boat. As such, all messages sent to or from the controller are sent/recieved with a type 10 message to/from A2, and then sent as their original message type to their destination (using the original message's sender/reciever IDs). Bluetooth Heartbeat and Error APIs exist to warn the user of a disconnected wireless link, and stop boat propulsion/steering. The full-team Rollcall API is used for debugging faulty communications.

### Bluetooth Control APIs

Message type 9 - Bluetooth Error:

||**Byte 1** |**Byte 2**|**Byte 3**|
| :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type |
| Variable Type | char | char | uint8_t |
| Min Value | B | A | 9 |
| Max Value | C | G | 9 |
| Example | C | G | 9 |

Message type 10 - Bluetooth Relay:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|**Byte 5**|**Byte 6**|**Byte 7**|
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Relay_Sender | Relay_Reciever | Relay_Type | Data |
| Variable Type | char | char | char | char | char | char | char |
| Min Value | B | B | 10 | A | A | 1 | 00000000 |
| Max Value | C | C | 10 | J | X | 12 | 11111111 |
| Example | C | B | 10 | I | A | 7 | 00110101 |

Message type 11 - Bluetooth Heartbeat:

||**Byte 1** |**Byte 2**|**Byte 3**|
| :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type |
| Variable Type | char | char | uint8_t |
| Min Value | B | B |11 |
| Max Value | C | C | 11|
| Example | B | C |11 |

### Bluetooth Relayed Messages (to boat)

Message type 1 - Set Steering Angle

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|
| :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Angle |
| Variable Type | char | char | uint8_t | uint8_t |
| Min Value | A | E |1 | 0 |
| Max Value | A | E | 1| 255|
| Example | A | E |1 | 125 | 

Message type 2 - Set Throttle Percentage:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|
| :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Throttle |
| Variable Type | char | char | uint8_t | uint8_t |
| Min Value | A | D |2 | 0 |
| Max Value | A | D | 2| 255|
| Example | A | D |2 | 125 | 

Message type 3 - Set Camera Angle:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|**Byte 5**|
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Yaw | Pitch |
| Variable Type | char | char | uint8_t | int8_t | int8_t |
| Min Value | A | G |5 | -128 | -128 |
| Max Value | A | G | 5| 127| 127 |
| Example | A | G |5 | 125 | 90 |

Message type 4 - Take Photo:

||**Byte 1** |**Byte 2**|**Byte 3**|
| :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type |
| Variable Type | char | char | uint8_t |
| Min Value | A | F |4 |
| Max Value | A | F | 4|
| Example | A | F |4 |

### Bluetooth Relayed Messages (to controller)

Message type 5 - Send Speed Data:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|
| :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Speed |
| Variable Type | char | char | uint8_t | uint8_t |
| Min Value | H | A |5 | 0 |
| Max Value | H | A | 5| 255|
| Example | H | A |5 | 125 | 

Message type 6 - Send Distance Data:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|
| :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Distance |
| Variable Type | char | char | uint8_t | uint8_t |
| Min Value | J | A |6 | 0 |
| Max Value | J | A | 6| 255|
| Example | J | A |6 | 125 | 

Message type 7 - Send Temperature Data:

||**Byte 1** |**Byte 2**|**Byte 3**|**Byte 4**|
| :-------: | :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type | Temperature |
| Variable Type | char | char | uint8_t | uint8_t |
| Min Value | I | A |7 | 0 |
| Max Value | I | A | 7| 255|
| Example | I | A |7 | 125 |

### Debugging

Message type 12 - Rolecall:

||**Byte 1** |**Byte 2**|**Byte 3**|
| :-------: | :-------: | :-------: | :-------: |
| Variable Name | Sender_ID | Reciever_ID | Message_Type |
| Variable Type | char | char | uint8_t |
| Min Value | A | X |12 |
| Max Value | J | X | 12|
| Example | A | J |12 |