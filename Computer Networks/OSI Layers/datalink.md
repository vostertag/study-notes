# Data Link Layer

### Table of Contents

[1. Introduction](#introduction)  
[2. LLC: Logical Link Control](#llc-logical-link-control)  
[3. MAC: Media Access Control](#mac-media-access-control)  
[4. Sources](#sources)

## Introduction

The **data link layer** is responsible for packaging data into **frames**, performing error detections and uniquely identifying network devices. It is made of two sublayers: **logical link control (LLC)** and **media access control (MAC)**.

## LLC: Logical Link Control

The **LLC** is the upper layer. It adds informations to the frame about **which network layer protocol is being used** (this is Multiplexing/De-Multiplexing). It can also provide **flow control** and **automatic repeat request (ARQ) error management** mechanisms.

## MAC: Media Access Control

The **MAC address** is a **48-bits** address assigned to a device's **network interface card (NIC)**. Every device has a **unique** MAC address, which is used to identify it. The first 24-bits are the vendor's code and the other 24-bits are a unique value for the card. It is represented by **six groups of two hexadecimal digits**, separated by hyphens (-) or colons (:) (example: ``` 01:23:45:67:89:ab ```).

The MAC sublayer will add a **header** and a **trailer** to the packet. The header will change in function of what media is used but is composed of:

* A **start frame**
* The **source and destination MAC address**
* Informations about the **type of data / length of the frame**

The **trailer**'s goals is to **find out if any error occured**. This is done by calculating a logical or mathematical sequence and placing it in the **Frame Check Sequence (FCS) field** of the trailer, that will be controled by the receiving end, which calculated his own FCS. If the two FCS doesn't match, an error occured. Finally, a **stop frame** field signals the end of the frame (if the length field of the header is note used).

![frame](https://qph.fs.quoracdn.net/main-qimg-29979db148e1d3a7192738e5c3b9f322)

Finally the **MAC sublayer** is responsible for the **collision resolution**, which can occur when multiple end nodes are connected to the same link. It makes sure that the link is used cooperatively with protocals such as CSMA/CD protocol.

## Sources

* [http://computernetworkingsimplified.in/data-link-layer/components-data-link-layer-llc-mac/](http://computernetworkingsimplified.in/data-link-layer/components-data-link-layer-llc-mac/)
* [https://www.youtube.com/watch?v=ePIRcNQf4d4](https://www.youtube.com/watch?v=ePIRcNQf4d4)
* [https://en.wikipedia.org/wiki/Data_link_layer](https://en.wikipedia.org/wiki/Data_link_layer)
* [https://www.youtube.com/watch?v=vj3ut2uGCgs](https://www.youtube.com/watch?v=vj3ut2uGCgs)
