![[Pasted image 20240701193759.png]]

Reverse proxies like nginx run on the main http port like port 80 and then direct the incoming backend request to the specific port it has to go to. For example if 2 processes are running on port 8080 and 8081, nginx will decide where to send the backend request coming all default 80 port. When no port number is mentioned, it means the default port '80' is being accessed. It helps in running two backend processes using different ports on the same port number.

![[Pasted image 20240701194017.png]]

proxy is the service through which VPN's work, they take the request to the desired destination through some other network so it seems like you are sitting in USA or some other country wherein in reality you are still in India.