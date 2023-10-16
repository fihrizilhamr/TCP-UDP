# TCP-UDP
## Pendahuluan

Repository ini dibentuk untuk menyelesaikan tugas Jaringan Komputer.

| Nama | NRP |
| :---: | :---: |
| Fihriz Ilham Rabbany | 5025211040 |

## Pembahasan Soal TCP

### Soal 1
What is the IP address and TCP port number used by the client computer (source)
that is transferring the alice.txt file to gaia.cs.umass.edu? To answer this
question, it’s probably easiest to select an HTTP message and explore the details
of the TCP packet used to carry this HTTP message, using the “details of the
selected packet header window” (refer to Figure 2 in the “Getting Started with
Wireshark” Lab if you’re uncertain about the Wireshark windows).

##### Jawaban
<img width="481" alt="Screenshot 2023-10-16 095954" src="https://github.com/fihrizilhamr/TCP-UDP/assets/116176265/2e8ae2a8-8bc2-4d79-a4ec-70fb8c635ea0">

IP address : 192.168.86.68
TCP port number : 55639

### Soal 2
What is the IP address of gaia.cs.umass.edu? On what port number is it sending
and receiving TCP segments for this connection?

##### Jawaban
<img width="476" alt="image" src="https://github.com/fihrizilhamr/TCP-UDP/assets/116176265/9be58b28-b633-4b90-a841-b55ae69cb8db">

IP address : 128.119.245.12 
Port number : 80

### Soal 3
What is the sequence number of the TCP SYN segment that is used to initiate the
TCP connection between the client computer and gaia.cs.umass.edu? (Note: this
is the “raw” sequence number carried in the TCP segment itself; it is NOT the
packet # in the “No.” column in the Wireshark window. Remember there is no
such thing as a “packet number” in TCP or UDP; as you know, there are sequence
numbers in TCP and that’s what we’re after here. Also note that this is not the
relative sequence number with respect to the starting sequence number of this
TCP session.). What is it in this TCP segment that identifies the segment as a
SYN segment? Will the TCP receiver in this session be able to use Selective
Acknowledgments (allowing TCP to function a bit more like a “selective repeat”
receiver, see section 3.4.5 in the text)?

##### Jawaban
<img width="482" alt="image" src="https://github.com/fihrizilhamr/TCP-UDP/assets/116176265/b2c3b257-515e-4431-8f0a-44398884e632">
Raw sequence : 4236649187

### Soal 4
What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu
to the client computer in reply to the SYN? What is it in the segment that
identifies the segment as a SYNACK segment? What is the value of the
Acknowledgement field in the SYNACK segment? How did gaia.cs.umass.edu
determine that value? 

##### Jawaban
<img width="484" alt="image" src="https://github.com/fihrizilhamr/TCP-UDP/assets/116176265/26c5e618-211e-4b78-9e0b-3a4b1a16ae64">

Raw sequence : 1068969752
Acknowledgement number (raw) : 4236649188

### Soal 5
What is the sequence number of the TCP segment containing the header of the
HTTP POST command? Note that in order to find the POST message header,
you’ll need to dig into the packet content field at the bottom of the Wireshark
window, looking for a segment with the ASCII text “POST” within its DATA
field. How many bytes of data are contained in the payload (data) field of this
TCP segment? Did all of the data in the transferred file alice.txt fit into this single
segment?

##### Jawaban
<img width="483" alt="image" src="https://github.com/fihrizilhamr/TCP-UDP/assets/116176265/92c5e607-160b-48bc-a287-1a4f450a7fd6">

Raw sequence : 4236649188 
TCP payload : 1448

### Soal 6
Consider the TCP segment containing the HTTP “POST” as the first segment in
the data transfer part of the TCP connection.
 At what time was the first segment (the one containing the HTTP POST) in
the data-transfer part of the TCP connection sent?
 At what time was the ACK for this first data-containing segment received?
 What is the RTT for this first data-containing segment?
 What is the RTT value the second data-carrying TCP segment and its ACK?
 What is the EstimatedRTT value (see Section 3.5.3, in the text) after the
ACK for the second data-carrying segment is received? Assume that in
making this calculation after the received of the ACK for the second segment,
4 Hint: this TCP segment is sent by the client soon (but not always immediately) after the SYNACK
segment is received from the server. 5 Note that if you filter to only show “http” messages, you’ll see that the TCP segment that Wireshark
associates with the HTTP POST message is the last TCP segment in the connection (which contains the
text at the end of alice.txt: “THE END”) and not the first data-carrying segment in the connection.
Students (and teachers!) often find this unexpected and/or confusing.
that the initial value of EstimatedRTT is equal to the measured RTT for the
first segment, and then is computed using the EstimatedRTT equation on
page 242, and a value of  = 0.125.
Note: Wireshark has a nice feature that allows you to plot the RTT for
each of the TCP segments sent. Select a TCP segment in the “listing of
captured packets” window that is being sent from the client to the
gaia.cs.umass.edu server. Then select: Statistics->TCP Stream Graph-
>Round Trip Time Graph.

##### Jawaban

### Soal 7 
What is the length (header plus payload) of each of the first four data-carrying
TCP segments?

##### Jawaban

### Soal 8 
What is the minimum amount of available buffer space advertised to the client by
gaia.cs.umass.edu among these first four data-carrying TCP segments7? Does the
lack of receiver buffer space ever throttle the sender for these first four datacarrying segments?

##### Jawaban

### Soal 9 
Are there any retransmitted segments in the trace file? What did you check for (in
the trace) in order to answer this question?

##### Jawaban

### Soal 10
How much data does the receiver typically acknowledge in an ACK among the
first ten data-carrying segments sent from the client to gaia.cs.umass.edu? Can
you identify cases where the receiver is ACKing every other received segment
(see Table 3.2 in the text) among these first ten data-carrying segments?

##### Jawaban

### Soal 11
What is the throughput (bytes transferred per unit time) for the TCP connection?
Explain how you calculated this value.

##### Jawaban


### Soal 12
Use the Time-Sequence-Graph(Stevens) plotting tool to view the sequence
number versus time plot of segments being sent from the client to the
gaia.cs.umass.edu server. Consider the “fleets” of packets sent around t = 0.025, t
= 0.053, t = 0.082 and t = 0.1. Comment on whether this looks as if TCP is in its
slow start phase, congestion avoidance phase or some other phase. Figure 6 shows
a slightly different view of this data.

##### Jawaban


### Soal 13
These “fleets” of segments appear to have some periodicity. What can you say
about the period?

##### Jawaban


### Soal 14
Answer each of two questions above for the trace that you have gathered when
you transferred a file from your computer to gaia.cs.umass.edu

##### Jawaban


### Soal 15
What is the throughput (bytes transferred per unit time) for the TCP connection?
Explain how you calculated this value.

##### Jawaban

## Pembahasan Soal UDP

### Soal 1
Select the first UDP segment in your trace. What is the packet number4 of this
segment in the trace file? What type of application-layer payload or protocol
message is being carried in this UDP segment? Look at the details of this packet
in Wireshark. How many fields there are in the UDP header? (You shouldn’t
look in the textbook! Answer these questions directly from what you observe in
the packet trace.) What are the names of these fields?

##### Jawaban

### Soal 2
By consulting the displayed information in Wireshark’s packet content field for
this packet (or by consulting the textbook), what is the length (in bytes) of each of
the UDP header fields?

##### Jawaban

### Soal 3
The value in the Length field is the length of what? (You can consult the text for
this answer). Verify your claim with your captured UDP packet. 

##### Jawaban

### Soal 4
What is the maximum number of bytes that can be included in a UDP payload?
(Hint: the answer to this question can be determined by your answer to 2. above)

##### Jawaban

### Soal 5
What is the largest possible source port number? (Hint: see the hint in 4.)

##### Jawaban

### Soal 6
What is the protocol number for UDP? Give your answer in decimal notation. To
answer this question, you’ll need to look into the Protocol field of the IP datagram
containing this UDP segment (see Figure 4.13 in the text, and the discussion of IP
header fields). 

##### Jawaban

### Soal 7
Examine the pair of UDP packets in which your host sends the first UDP packet
and the second UDP packet is a reply to this first UDP packet. (Hint: for a second
packet to be sent in response to a first packet, the sender of the first packet should
be the destination of the second packet). What is the packet number5 of the first
of these two UDP segments in the trace file? What is the packet number6 of the
second of these two UDP segments in the trace file? Describe the relationship
between the port numbers in the two packets. 

##### Jawaban
