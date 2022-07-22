# DEvops_Websocket
It's a readme about websocket




WebSocket is a computer communications protocol, providing full-duplex communication channels over a single TCP connection. The WebSocket protocol was standardized by the IETF as RFC 6455 in 2011. The current API specification allowing web applications to use this protocol is known as WebSockets.[1] It is a living standard maintained by the WHATWG and a successor to The WebSocket API from the W3C.



WebSocket is distinct from HTTP. Both protocols are located at layer 7 in the OSI model and depend on TCP at layer 4. Although they are different, RFC 6455 states that WebSocket "is designed to work over HTTP ports 443 and 80 as well as to support HTTP proxies and intermediaries", thus making it compatible with HTTP. To achieve compatibility, the WebSocket handshake uses the HTTP Upgrade header to change from the HTTP protocol to the WebSocket protocol.

The WebSocket protocol enables interaction between a web browser (or other client application) and a web server with lower overhead than half-duplex alternatives such as HTTP polling, facilitating real-time data transfer from and to the server. This is made possible by providing a standardized way for the server to send content to the client without being first requested by the client, and allowing messages to be passed back and forth while keeping the connection open. In this way, a two-way ongoing conversation can take place between the client and the server. The communications are usually done over TCP port number 443 (or 80 in the case of unsecured connections), which is beneficial for environments that block non-web Internet connections using a firewall. Similar two-way browser–server communications have been achieved in non-standardized ways using stopgap technologies such as Comet or Adobe Flash Player.




Most browsers support the protocol, including Google Chrome, Firefox, Microsoft Edge, Internet Explorer, Safari and Opera.[5]

Unlike HTTP, WebSocket provides full-duplex communication.[6][7] Additionally, WebSocket enables streams of messages on top of TCP. TCP alone deals with streams of bytes with no inherent concept of a message. Before WebSocket, port 80 full-duplex communication was attainable using Comet channels; however, Comet implementation is nontrivial, and due to the TCP handshake and HTTP header overhead, it is inefficient for small messages. The WebSocket protocol aims to solve these problems without compromising the security assumptions of the web.

The WebSocket protocol specification defines ws (WebSocket) and wss (WebSocket Secure) as two new uniform resource identifier (URI) schemes that are used for unencrypted and encrypted connections respectively. Apart from the scheme name and fragment (i.e. # is not supported), the rest of the URI components are defined to use URI generic syntax.

Using browser developer tools, developers can inspect the WebSocket handshake as well as the WebSocket frames.




// Creates new WebSocket Object with a wss uri as the parameter
const socket = new WebSocket('wss://game.example.com/ws/updates');

// Fired when a connection with a WebSocket is opened

socket.onopen = function () {
	setInterval (function() {
		if(socket.bufferedAmount == 0)
			socket.send(getUpdateData());
	}, 50);
};

// Fired when data is received through a WebSocket

socket.onmessage = function(event) {
	handleUpdateData(event.data);
}

// Fired when a connection with a WebSocket is closed
socket.onclose = function(event) {
	onSocketClose(event);
};

// Fired when a connection with a WebSocket has been closed because of an error

socket.onerror = function(event){
	onSocketError(event);
};

Once a connection has been established between the client and the server, the open event is fired from Web Socket instance. It is called as the initial handshake between client and server.

The event, which is raised once the connection is established, is called the onopen. Creating Web Socket connections is really simple. All you have to do is call the WebSocket constructor and pass in the URL of your server.

The following code is used to create a Web Socket connection −

// Create a new WebSocket.
var socket = new WebSocket('ws://echo.websocket.org');

Once the connection has been established, the open event will be fired on your Web Socket instance.

onopen refers to the initial handshake between client and the server which has lead to the first deal and the web application is ready to transmit the data.

The following code snippet describes opening the connection of Web Socket protocol −

socket.onopen = function(event) {
   console.log(“Connection established”);
   // Display user friendly messages for the successful establishment of connection
   var.label = document.getElementById(“status”);
   label.innerHTML = ”Connection established”;
}

It is a good practice to provide appropriate feedback to the users waiting for the Web Socket connection to be established. However, it is always noted that Web Socket connections are comparatively fast.




# How WebSocket works ?

WebSockets provide a persistent connection between a client and server that both parties can use to start sending data at any time. The client establishes a WebSocket connection through a process known as the WebSocket handshake. This process starts with the client sending a regular HTTP request to the server.







