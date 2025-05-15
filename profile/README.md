Profile picture by [trevordark on Wallhaven](https://wallhaven.cc/user/trevordark)

```zenuml
zenuml
    title Order Service
    Client #FFEBE6
    API #0747A6
    OrderService #E3FCEF
    group BusinessService {
      PurchaseService
      InvoiceService
    }

    @Starter(Client)
    // `POST /orders`
    API.post(payload) {
      OrderService.create(payload) {
        order = new Order(payload)
        if(order != null) {
          par {
            PurchaseService.createPO(order)
            InvoiceService.createInvoice(order)      
          }      
        }
      }
    }
    
```
