1. Install the `axios` package by running the following command in your Angular project directory:
```shell
npm install axios
```

2. Create a new component file (e.g., `example.component.ts`) and add the following code:

```typescript
import { Component, OnInit } from '@angular/core';
import axios from 'axios';

interface Post {
  id: number;
  title: string;
  body: string;
}

@Component({
  selector: 'app-example',
  template: `
    <ul>
      <li *ngFor="let post of posts">{{ post.title }}</li>
    </ul>
  `,
})
export class ExampleComponent implements OnInit {
  posts: Post[];

  ngOnInit() {
    axios.get<Post[]>('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
        this.posts = response.data;
      })
      .catch(error => {
        console.error('Error fetching posts:', error);
      });
  }
}
```

In this example, we're importing the `axios` library to make the HTTP request. The `Post` interface represents the structure of the JSON response from the API, including `id`, `title`, and `body` properties.

Inside the `ngOnInit` method, we make an HTTP GET request to `https://jsonplaceholder.typicode.com/posts` to fetch a list of posts. Upon a successful response, the retrieved data is stored in the `posts` array. Then, we use `ngFor` to iterate over the `posts` array and display the `title` property of each post in a list.
