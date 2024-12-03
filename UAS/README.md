# UAS-JARKOM

# TCP Analysis for Sample Capture HTTP

This document provides answers to a set of questions based on the TCP segments captured in the trace file `tcp-ethereal-trace-1` found in the [Wireshark Trace Files](http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip). The analysis focuses on the TCP segments exchanged between a client and the server `gaia.cs.umass.edu`.

## Questions and Answers

### 1. What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu? (10%)

**Answer:**

![UAS1](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas1.jpg)


- **Source IP:** 192.168.1.102
- **Source Port:** 1161
- **Destination IP:** 128.119.245.12
- **Destination Port:** 80

### 2. What does gaia.cs.umass.edu use the IP address and port number to receive the file? (Attach the screenshot of your Wireshark's display) (10%)

**Answer:**

![UAS2](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas%202.jpg)


- **Destination IP:** 128.119.245.12
- **Destination Port:** 80

### 3. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment? (Attach the screenshot of your Wireshark's display) (10%)

**Answer:**

![UAS3](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas%203.jpg)


- **Sequence Number:** 0
- **Flag:** SYN (Set)

### 4. What is the sequence number of the SYN-ACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the Acknowledgement field in the SYN-ACK segment? How did gaia.cs.umass.edu determine that value? What is it in the segment that identifies the segment as a SYN-ACK segment? (Attach the screenshot of your Wireshark's display) (10%)

**Answer:**

![UAS4](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas%204.jpg)


- **Sequence Number:** 0
- **Acknowledgement Number:** 1
- **Flag:** SYN and ACK (This identifies the segment as a SYN-ACK)

### 5. What is the sequence number of the TCP segment containing the HTTP POST command? Note that in order to find the POST command, you’ll need to dig into the packet content field at the bottom of the Wireshark window, looking for a segment with a “POST” within its DATA field. (Attach the screenshot of your Wireshark's display) (15%)

**Answer:**

![UAS5](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas%205.jpg)


- **Sequence Number:** 1
- **Flags:** PSH, ACK (The client sends the POST command)

### 6. Consider the TCP segment containing the HTTP POST as the first segment in the TCP connection. What are the sequence numbers of the first six TCP connection segments (including the HTTP POST segment)? At what time was each segment sent? When was the ACK for each segment received? Given the difference between when each TCP segment was sent, and when its acknowledgement was received, what is the RTT value for each of the six segments? What is the EstimatedRTT value (see page 237 in the textbook) after the receipt of each ACK? Assume that the value of the EstimatedRTT is equal to the measured RTT for the first segment, and then is computed using the EstimatedRTT equation on page 237 for all subsequent segments. (30%)

**Answer:**

![UAS6](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas6.jpg)


The sequence numbers for the first six TCP connection segments (including the HTTP POST) are as follows:

1. **1st Sequence Number:** 1
2. **2nd Sequence Number:** 566
3. **3rd Sequence Number:** 2026
4. **4th Sequence Number:** 3486
5. **5th Sequence Number:** 4946
6. **6th Sequence Number:** 6406

**Time each segment was sent:**
- 1st Time: 0.053937
- 2nd Time: 0.077294
- 3rd Time: 0.124085
- 4th Time: 0.169118
- 5th Time: 0.217299
- 6th Time: 0.267802

**RTT values:**

Formula: RTT = ACK received time - Sent time

- **1st RTT:** 27.5 ms
- **2nd RTT:** 35.5 ms
- **3rd RTT:** 70 ms
- **4th RTT:** 114.5 ms
- **5th RTT:** 139.9 ms
- **6th RTT:** 189.8 ms

**Estimated RTT:** Use the formula from the textbook to calculate Estimated RTT after each ACK. For the first segment, it is equal to the measured RTT. For subsequent segments, use the Estimated RTT formula to update the value after each ACK.

You can use Wireshark’s "Statistics -> TCP Stream Graph -> Round Trip Time Graph" feature to visualize RTT values.

### 7. What is the length of each of the first six TCP segments? (Attach the screenshot of your Wireshark's display) (15%)

**Answer:**

![UAS7](https://github.com/Harrydhe/UAS-S2/blob/main/assets/uas%207.jpg)


The length of each of the first six TCP segments is as follows:

- **1st Length:** 565 bytes
- **2nd Length:** 1460 bytes
- **3rd Length:** 1460 bytes
- **4th Length:** 1460 bytes
- **5th Length:** 1460 bytes
- **6th Length:** 1460 bytes


