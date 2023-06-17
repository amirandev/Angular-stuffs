To dynamically set the page title from a component in an Angular application, you can use the `Title` service provided by `@angular/platform-browser`. Here's an example of how you can achieve this:

1. In the component where you want to set the page title (e.g., `example.component.ts`), import the `Title` service from `@angular/platform-browser`.

   ```typescript
   import { Component, OnInit } from '@angular/core';
   import { Title } from '@angular/platform-browser';

   @Component({
     selector: 'app-example',
     templateUrl: './example.component.html',
     styleUrls: ['./example.component.css']
   })
   export class ExampleComponent implements OnInit {
     constructor(private titleService: Title) {}

     ngOnInit(): void {
       // Set the page title
       this.titleService.setTitle('Example Page');
     }
   }
   ```

   In the `ngOnInit` lifecycle hook or any other appropriate method, call the `setTitle` method of the `Title` service and pass the desired page title as a parameter.

2. Make sure to include the component in the routing configuration and navigate to that component.

   ```typescript
   import { NgModule } from '@angular/core';
   import { Routes, RouterModule } from '@angular/router';
   import { ExampleComponent } from './example.component';

   const routes: Routes = [
     {
       path: 'example',
       component: ExampleComponent
     }
   ];

   @NgModule({
     imports: [RouterModule.forRoot(routes)],
     exports: [RouterModule]
   })
   export class AppRoutingModule {}
   ```
