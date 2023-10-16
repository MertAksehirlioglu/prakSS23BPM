# prakSS23BPM

This project implements a remote order receiving system, comprising a Node.js and Express-based server and a Vue.js and Nuxt-powered client. The objective is to enable users to place orders for various items remotely through the client interface. Client passes the customer requests to the server, which processes the orders and sends on to the CPEE engine. It uses Server-Sent Events (SSE) to provide real-time updates to clients about the server's state. The server also communicates with a third-party API to fetch image links for the available items.

## How it works?

Steps: 

1. Configure an instance in CPEE Engine (See [example instance](https://cpee.org/flow/?monitor=https://cpee.org/flow/engine/18252/) )
  - Add getOrder Endpoint: "https://lehre.bpm.in.tum.de/ports/22950/getOrder"
  - Add availableItems Data Element
  - Insert Service Call with Scripts and configure parameters

2. Generate and deploy client build files to .public folder (For details see [client repository](https://github.com/MertAksehirlioglu/prakss23))
   ``` bash
   npm run generate
   ```
  
3. Start server (For details see [server repository](https://github.com/MertAksehirlioglu/prakss23server) )
   ``` bash
   npm run start
   ```
4. Start CPEE instance
5. CPEE instance sends getOrder request to server.
6. Server updates status.
7. Client renders available state.
8. User selects drink, types name and clicks on submit order.
9. Client sends the order to server.
10. Server sends the order to callback address.
11. CPEE Engine processes the order request
12. Back to Step 5
     

## Activity Diagram

![activity drawio](https://github.com/MertAksehirlioglu/prakSS23BPM/assets/23525970/30d99383-dc4d-42ae-b1b9-f944522e6ceb)
