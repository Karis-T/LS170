```
https://amazon.com/Double-Stainless-Commercial-Refrigerator/B60HON32?ie=UTF8&qid=142952676&sr=93&keywords=commercial+fridge
```

1. Identify the host: `amazon.com`
2. Identify the names of the **query parameters**: `ie, qid, sr, keywords`
3. Identify the values of the **query parameters**: `UTF8, 142952676, 93, commercial+fridge`
4. Identify the scheme: `https` 
5. identify the path: `/Double-Stainless-Commercial-Refrigerator/B60HON32`
6. Identify the port : doesn't have one



1. add port `3000` to following URL:

```
http://amazon.com:3000/products/B60HON32?qid=142952676&sr=93
```



```
http://localhost:4567/todos/15
```

1. Identify the names of the **query parameters**: doesn't have any
2. Identify the scheme: `http` 
3. identify the path: `/todos/15`
4. identify the host: `localhost`
5. Identify the port : `4567`

1. What are two different ways to encode a space in a query parameter?: `%20` or ` +` 
2. What character indicates the beginning of a URL's query parameters? `?`
3. What character is used between the name and value of a query parameter? `=`
4. What character is used between multiple query parameters? `&`

1. What are the required components of an HTTP request? What are the additional optional components? 
   - Host name, Method and Path, http version are required components
   - Parameters, headers and body are optional components
2. What are the required components of an HTTP response? What are the additional optional components?
   - Status is required components
   - header & body are optional components
3. use `GET` to retrieve resources from the server "read only operations" search forms are used with get. Use `POST` when you want to send or change values stored on the server

