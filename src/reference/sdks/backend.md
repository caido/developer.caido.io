## Plugin Backend SDK

The examples below demonstrate usage of the various services and functionalities.

## api

Used to communicate between the frontend and backend.

### To send an event to the frontend:

```ts
sdk.api.send("eventName", 5, "hello");
```

### To register a new backend function:

```ts
sdk.api.register("multiply", (sdk: SDK, a: number, b: number) => {
    return a * b;
});
```

## events

Used to register an asynchronous callback to an intercepted request or response.

### To register a callback function on new intercepted requests:

```ts
sdk.events.onInterceptRequest((sdk: SDK, request: Request) => {
    // Do something with the request.
});
```

### To register a callback function on new intercepted responses:

```ts
sdk.events.onInterceptResponse((sdk: SDK, request: Request, response: Response) => {
    // Do something with the request/response.
});
```

## meta

Used to store plugin related data.

### To store plugin related data in the Caido data directory:

```ts
sdk.meta.path();
```

### To store plugin related data in an SQLite database in the Caido data directory:

```ts
sdk.meta.db();
```
