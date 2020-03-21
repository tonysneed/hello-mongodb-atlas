# Hello MongoDB Atlas

Using MongoDB Atlas with .NET Core

1. [Create MongoDB Altas Cluster](https://docs.atlas.mongodb.com/getting-started/)
   - Create an [account](https://docs.atlas.mongodb.com/tutorial/create-atlas-account/) and sign into MongoDB Atlas.
   - Deploy a [free-tier cluster](https://docs.atlas.mongodb.com/tutorial/deploy-free-tier-cluster/).
   - Secure your cluster.
     - Whitelist your current IP address.
     - Create a new user: username `test-user`, password `Str0ngPa$$w0rd`.
   - Download and install MongoDB Compass
     - Copy connection string, insert password, and create new connection.
2. Connect using MongoDB shell.
   - Use Docker to run MongoDB locally.
    ```
    docker run --name mongo -d -p 27017:27017 mongo
    docker exec -it mongo bash
    ```
   - Paste MongoDB shell connection string.
   - Provide password when prompted.
3. Create the database, add a collection, insert data.
    ```
    use BookstoreDb
    db.createCollection("Books")
    db.Books.insertMany([{"Name":"Design Patterns","Price":54.93,"Category":"Computers","Author":"Ralph Johnson"},{"Name":"Clean Code","Price":43.15,"Category":"Computers","Author":"Robert C. Martin"}])
    db.createCollection("Authors")
    db.Authors.insertMany([{"Name":"Ralph Johnson","Country":"United States"},{"Name":"Robert C. Martin","Country":"United Kingdom"}])
    ```
3. Connect programmatically from a .NET app.
   - Copy the app connection string, insert the password.
   - Paste into appSettings.json file.
    > **Note**: Avoid storing credentials in source code.
    > Use [secrets manager](https://docs.microsoft.com/en-us/aspnet/core/security/app-secrets?view=aspnetcore-3.1&tabs=windows) instead.
