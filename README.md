# prakSS23BPM

This project implements a remote order receiving system, comprising a Node.js and Express-based server and a Vue.js and Nuxt-powered client. The objective is to enable users to place orders for various items remotely through the client interface. Client passes the customer requests to the server, which processes the orders and sends on to the CPEE engine. It uses Server-Sent Events (SSE) to provide real-time updates to clients about the server's state. The server also communicates with a third-party API to fetch image links for the available items.

## How it works?

1.Configure an instance in CPEE Engine (See https://cpee.org/flow/?monitor=https://cpee.org/flow/engine/18252/ example instance)
  a. Add getOrder Endpoint: "https://lehre.bpm.in.tum.de/ports/22950/getOrder"
  b. Add availableItems Data Element
  b. Insert Service Call with Scripts and configure parameters

2. Generate and deploy client build files to .public folder (For details see client repository)
   ``` bash
   npm run generate
   ```
  
4. Start server (For details see server repository)
   ``` bash
   npm run start
   ```
5. Start CPEE instance
6. CPEE instance sends getOrder request to server.
7. Server updates status.
8. Client renders available state.
9. User selects drink, types name and clicks on submit order.
10. Client sends the order to server.
11. Server sends the order to callback address.
12. CPEE Engine processes the order request
13. Back to Step 6
     


CPEE Engine sends

## Activity Diagram

![activity drawio](https://github.com/MertAksehirlioglu/prakSS23BPM/assets/23525970/30d99383-dc4d-42ae-b1b9-f944522e6ceb)
