Profile picture by [trevordark on Wallhaven](https://wallhaven.cc/user/trevordark)

```zenuml
zenuml
    title API Infrastructure
    Client
    API
    Database

    @Starter(Client)
    // `GET /search`
    API.get(query) {
      Database.fetch(query) {
        if(result != None) {
          API.respond {
            Client.respond
          }     
        }
      }
    }
```
