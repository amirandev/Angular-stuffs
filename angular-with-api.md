To use the Angular HTTP client, follow these steps:

1. Import the HTTP client module in your Angular component or service file:
```typescript
import { HttpClient } from '@angular/common/http';
```

2. Inject the `HttpClient` service into your component's constructor or service:
```typescript
constructor(private http: HttpClient) { }
```

3. Use the `http` service to make API requests. For example, to make a GET request:
```typescript
this.http.get('https://api.example.com/data').subscribe(
  response => {
    // Handle the response data
  },
  error => {
    // Handle any errors
  }
);
```

4. You can also make other types of requests like POST, PUT, DELETE, etc. using the corresponding methods of the `http` service (`post()`, `put()`, `delete()`, etc.). Additionally, you can set request headers, pass request data, and handle the response data as per your API's requirements.
