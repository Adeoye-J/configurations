

\## vercel.json



Vercel json config for express backend



```bash

&#x20; {

&#x20;   "version": 2,

&#x20;   "builds": \[

&#x20;       {

&#x20;           "src": "server.js",

&#x20;           "use": "@vercel/node",

&#x20;           "config": {

&#x20;               "includeFiles": \[

&#x20;                   "dist/\*\*"

&#x20;               ]

&#x20;           }

&#x20;       }

&#x20;   ],

&#x20;   "routes": \[

&#x20;       {

&#x20;           "src": "/(.\*)",

&#x20;           "dest": "server.js"

&#x20;       }

&#x20;   ]

}

```



Vercel json config to support React Router in frontend



```bash

&#x20; {

&#x20;   "rewrites": \[

&#x20;     {

&#x20;       "source": "/(.\*)",

&#x20;       "destination": "/"

&#x20;     }

&#x20;   ]

&#x20; }

```



