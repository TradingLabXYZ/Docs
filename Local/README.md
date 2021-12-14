# How to run TradingLab on Local

In order to run TradingLab locally three environments need to be prepared:

1. Frontend Nodejs webserver
2. Backend Golang webserver 
3. Blockchain Moonbeam Dev Node

Requirements: NodeJs, Golang and Docker installed.

Fronend runs on port 9000.

Backend runs on port 8080.

When everything is done, open http://localhost:9000 on your browser.

To contribute, set up a branch and then submit the code.

## Frontend

### 1 --> Open a new terminal

### 2 --> Only the first time run

```bash
npm install
```

### 3 --> Every time run

```bash
npm run serve
```

## Backend

### 1 --> Open a new terminal

### 2 --> Only the first time run

```bash
go build
```

### 3 --> Set environments variables

#### windows

```cmd
set TL_APP_ENV=
set TL_DB_USER=
set TL_DB_PASS=
set TL_DB_HOST=
set TL_DB_PORT=
set DO_KEY=
set DO_SECRET=
set CDN_PATH=
set ADMIN_TOKEN=
```

#### linux 

```bash
export TL_APP_ENV=
export TL_DB_USER=
export TL_DB_PASS=
export TL_DB_HOST=
export TL_DB_PORT=
export DO_KEY=
export DO_SECRET=
export CDN_PATH=
export ADMIN_TOKEN=
```

### 4 --> Every time run

```bash
go run .
```

## Blockchain

### 1 --> Open a new terminal

### 2 --> Only the first time run 

```bash
docker pull purestake/moonbeam:v0.16.0
``` 

### 3 --> Only the first time add Moonbeam Dev Network to Metamask: 

**Network Name**: Moonbeam Dev

**RPC URL**: http://127.0.0.1:9933

**ChainID**: 1281 ((hex: 0x501))

**Symbol (Optional)**: DEV

**Block Explorer (Optional)**: https://moonbeam-explorer.netlify.app/

### 4 --> Every time run

#### windows

```bash
docker run --rm --name moonbeam_development -p 9944:9944 -p 9933:9933 ^
purestake/moonbeam:v0.16.0 ^
--dev --ws-external --rpc-external
```

#### linux

```bash
docker run --rm --name moonbeam_development --network host \
purestake/moonbeam:v0.16.0 \
--dev
```
