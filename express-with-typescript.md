\## Guide to Setup Up a Basic Express Server with TypeScript



This guide provides a step-by-step process for setting up a basic web server using Express.js and TypeScript.

Prerequisites

Ensure you have the following installed:



Node.js ( Latest LTS recommended )

npm (or yarn/pnpm)



\### 1. Project Initialization



Start by creating a new directory for your project and initializing a new Node.js project.



```bash

mkdir server

```



```bash

cd server

```



```bash

npm init -y

```



\### 2. Install Dependencies



Install Express and the necessary TypeScript-related packages.

Production Dependencies



Install Express, the web framework



```bash

npm install express cors dotenv

```



Install TypeScript, the type definitions for Express and Node.js, and `tsx` for running the server without a pre-compiled step.



```bash

npm install -D typescript tsx @types/node ts-node @types/express nodemon @types/cors

```



\### 3. Configure TypeScript



Create a `tsconfig.json` file in your project root to configure the TypeScript compiler. You can generate a default file using the following command



```bash

npx tsc --init

```



For a basic setup, ensure your `tsconfig.json` has at least these settings:



```json

{

&#x20;   "compilerOptions": {

&#x20;       "target": "ES2020",

&#x20;       "module": "nodenext",

&#x20;       "moduleResolution":"nodenext",

&#x20;       "outDir": "./dist",

&#x20;       "rootDir": "./",

&#x20;       "strict": true,

&#x20;       "esModuleInterop": true,

&#x20;       "skipLibCheck": true,

&#x20;       "forceConsistentCasingInFileNames": true

&#x20;   },

&#x20;   "include": \[

&#x20;       "./\*\*/\*.ts"

&#x20;   ],

&#x20;   "exclude": \[

&#x20;       "node\_modules"

&#x20;   ]

}

```



\### 4. Create the Server File



Create a main server file, for example `server.ts`.



Add the following basic Express server code to server.ts:



```typescript

import "dotenv/config";

import express, { Request, Response } from 'express';

import cors from "cors";



const app = express();



// Middleware

app.use(cors())

app.use(express.json());



const port = process.env.PORT || 3000;



app.get('/', (req: Request, res: Response) => {

&#x20;   res.send('Server is Live!');

});



app.listen(port, () => {

&#x20;   console.log(`Server is running at http://localhost:${port}`);

});

```



\### 5. Update package.json Scripts



Modify your `package.json` file to add scripts for starting the server using `tsx`



```json

"scripts": {

&#x20;   "start": "tsx server.ts",

&#x20;   "server": "nodemon --exec tsx server.ts",

&#x20;   "build": "tsc"

}

```



```json

"type": "module"

```



\### 6. Run the Server



Start your server using the new script:



```bash

npm run server

```



You should see the message: Server is running at http://localhost:3000



Open your web browser and navigate to http://localhost:3000 to see the



"Server is Live!" message.

