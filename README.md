# prakSS23BPM

This project implements a remote order receiving system, comprising a Node.js and Express-based server and a Vue.js and Nuxt-powered client. The objective is to enable users to place orders for various items remotely through the client interface. Client passes the customer requests to the server, which processes the orders and sends on to the CPEE engine. It uses Server-Sent Events (SSE) to provide real-time updates to clients about the server's state. The server also communicates with a third-party API to fetch image links for the available items. 
