# To build

```bash
docker build -t {name} . 
```
in both directories

Drink a coffee
# To run the site

```bash
docker run -p 3000:3000 {name}
```
# To run the api
```bash
docker run --env-file .env -p 1337:1337 {name}
```


If it is the first time running the api you have to publish each article, I have no idea why the seed doesnt publish, as well as change the role permissions to include upload get permissions
The api can be accessed by the link given, the user should remain but if it doesnt register a new user to edit it.


