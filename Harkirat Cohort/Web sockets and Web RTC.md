Web sockets are a way to communicate with a server in a full duplex mode and the communication is persistent. It uses TCP protocol so makes sure all data is transferred. Generally used for chat-based applications known as sockets. Popular framework built on web sockets- sockets.io 

Web-RTC, is yet another mode of full duplex communication between a browser and another browser aka Peer-to-peer communication. Browser directly talks with another browser without any server in between. Uses UDP protocol as it can allow some frames to be missed. Generally used for video calling applications.

To first let the browser know their IP and port number to send to other browser they make use of a STUN server.

![[Pasted image 20240421184142.png]]

![[Pasted image 20240421184303.png]]

`Ice Candidates` - `Ip:Port` pair we get through STUN server is called ice candidates.

![[Pasted image 20240421192647.png]]

![[Pasted image 20240421192746.png]]

For establishing connection between 2 browsers to send ice candidates, the browsers make a connection using a web socket server, Browser A stores their details in `local description` and sends it to browser to via web sockets and then browser to saves those details as their `remote description` and vice versa

All of this is done using `SDP` - session description protocol








