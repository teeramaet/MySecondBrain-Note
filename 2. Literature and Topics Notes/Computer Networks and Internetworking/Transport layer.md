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


