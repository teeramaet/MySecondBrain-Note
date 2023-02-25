## Principle of reliable data transfer

	Normally data is sent through unreliable channel. Complexity depend on characteristic of the channel. 

## Structure of making reliable data transfer
1. rdt_send()
2. udt_send()
3. deliverer_data()
4. rdt_rcv()

## Explain in terms of finite state machine
From rdt1.0 - rdt3.0 we use stop and wait  concept
	- sender sends one packet, then waits for receiver response.
Ex1. (rdt 1.0) no bits errors, no loss of packets
normal proces
APP -> API -> socket -> UDP
	![[Pasted image 20230225030601.png]]

Ex2. (rdt 2.0) bit errors
reciever send ACKs if it's OK
receiver send NAKs if it isn't OK so that sender retransmits packet again

##### Cons
- When ACK/NAK corrupted (cannot resend because it will create duplicate at receiver side)

Ex2.1 handling corrupted ack/nak by using sequence 0/1 packet

Ex2.2 NAK is too complicate (remove NAK)
include seq of ACK 
**TCP use this structure**

Ex3 channel contain both error and loss
adding the timeout

Ex3.1 pipeline 
size of window controlled by congestion and flow control

increase utilization
introduce window of up to N (Go-Back-N)
1 2 3 4 5 -> 2 failed

Go back n: retransmit 2 3 4 5
Selective repeat: only send 2 use buffer

## Port number
dest port always fixed
Os assign source port

#### Type 
well-known port
registered port
private and dynamic port 
	for OS

speed of sender controlled by flow control (yellow part)




