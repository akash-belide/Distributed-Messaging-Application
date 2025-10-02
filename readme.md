# Multi-client Distributed Real-time Chat Application (Room-based)

Supports **unicast**, **multicast**, and **broadcast** messaging.

The backend is **distributed** and **horizontally scalable**.  
Technologies used:
- Socket.io (WebSocket communication)  
- Redis (cache + pub/sub for server sync)  
- HAProxy (load balancer)  
- MongoDB (persistent storage)  

---

## Setup

### Backend

The system requires **Redis**, **MongoDB**, and **HAProxy**.  
A `docker-compose.yml` file is provided in the `backend` directory to pull containers, build the backend, and expose ports.

```bash
# move into backend folder
cd backend

# build backend image
docker build -t chatapp .

# start services
docker-compose up   # add -d for detached mode

# stop services
docker-compose down
````

---

### Frontend

The main logic (WebSocket handling and API calls) is in `App.js`.
Make sure backend services are running before starting the frontend.

```bash
# run development server
npm start

# build and serve production assets
npm run build && serve ./build
```

