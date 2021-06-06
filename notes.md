[nuxt-editing-ports-docs]: https://nuxtjs.org/docs/2.x/features/configuration#edit-host-and-port
### Editing Nuxt Ports (and Hosts if Needed)
- for one reason or another (main one being the port is taken) we need to define our own port for our nuxt application
- this is very good [documentation][nuxt-editing-ports-docs] on how to do this
  - to summarise, it is not wise to do this in your nuxt config file
  - that looks something like this:
  - instead, it is advised to define this in your package.json file

     ```javascript 
     "scripts": {
        "dev:host": "nuxt --hostname '0' --port 8000"
    }
    ```
  - or when you start up your dev environment in your terminal
  - like this: 
    
    ```javascript 
    HOST=0 PORT=8000 npm run dev
    ```
- i am not touching on the hostname configuration ettiquete, but the same link previously included can be consulted to learn about it.
