### Adding Bootstrap to Angular 2 project

Provided you use the Angular-CLI to generate new projects, there's another way to make bootstrap accessible in Angular 2/4.

* Via command line interface navigate to the project folder. Then use npm to install bootstrap:
`$ npm install --save bootstrap` . The --save option will make bootstrap appear in the dependencies.

* Edit the *.angular-cli.json* file, which configures your project. It's inside the project directory. Add a reference to the "styles" array. The reference has to be the relative path to the bootstrap file downloaded with npm, e.g.: "../node_modules/bootstrap/dist/css/bootstrap.min.css",

##### For Ng-Bootstrap 4 need to install Bootstrap CSS first:

<https://medium.com/codingthesmartway-com-blog/using-bootstrap-with-angular-c83c3cee3f4a>

1. ```$ npm install  --save @ng-bootstrap/ng-bootstrap ```
 Bootstrap 4 requires Bootstrap CSS to be added: 
`$ npm install bootstrap@4.0.0-alpha.6 --save`

2. Now we need to add *bootstrap.min.js* , *jquery.min.js* and *bootstrap.min.css* to  **.angular-cli.json** file:
```
"styles": [
    "styles.css",
    "../node_modules/bootstrap/dist/css/bootstrap.min.css"
  ],
  "scripts": [
    "../node_modules/jquery/dist/jquery.min.js",
    "../node_modules/bootstrap/dist/js/bootstrap.min.js"
  ],
```
3. Import Ng-Bootstrap main module *NgbModule*  to *app.module.ts*:
`import {NgbModule} from '@ng-bootstrap/ng-bootstrap';`
Add this module to the imports array in *@NgModule* decorator. If you want to import NgbModule in your root module (e.g. AppModule) you need to call the forRoot() factory method, as you can see in the following:
```
@NgModule({
  declarations: [AppComponent, ...],
  imports: [NgbModule.forRoot(), ...],
  bootstrap: [AppComponent]
})
export class AppModule {
}
```
If you want to add it in other modules (e.g. child modules of root module) don't need to call *forRoot()*
```
@NgModule({
  declarations: [OtherComponent, ...],
  imports: [NgbModule, ...]
})
export class OtherModule {
}
```

If you see error message about Tether add it to **.angular-cli.json** :
```
"scripts": [
          "../node_modules/jquery/dist/jquery.js",
          "../node_modules/tether/dist/js/tether.js",
          "../node_modules/bootstrap/dist/js/bootstrap.js"
           ],
```



To uninstall:
`$ npm uninstall bootstrap --save`

