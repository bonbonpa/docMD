#
Vue 2.0 and Laravel 5.3

[ref youtube](https://www.youtube.com/watch?v=WKSP8knLPyE&index=3&list=PL3ZhWMazGi9IommUd5zQmjyNeF7s1sP7Y
)
## basic laravel and vuejs2

### Vue 2.0 and Laravel 5.3 #3 Windows Installation
[ref youtube](https://www.youtube.com/watch?v=WKSP8knLPyE&index=3&list=PL3ZhWMazGi9IommUd5zQmjyNeF7s1sP7Y)

#### Install VueJS Global

```
$ npm install -g vue-cli
```
#### Install webpack vue

```
$ vue init webpack-simple (projectname)
$ npm install
$ npm run dev

web run at http://localhost:8080/
```
### Vue 2.0 and Laravel 5.3 #4 Homepage
[ref youtube](https://www.youtube.com/watch?v=dAjwfX4Ko48&list=PL3ZhWMazGi9IommUd5zQmjyNeF7s1sP7Y&index=4)

#### Go to src/main.js

```javascript
import Vue from 'vue'
import App from './App.vue'

new Vue({
el: '#app',
render: h => h(App)
})
```

### Vue 2.0 and Laravel 5.3 #5 Intro to Components

create folder **components** in src -> **src/components** and create Navbar.vue in components -> **src/components/Navbar.vue**

go to **Navbar.vue** and code line

```html
<template>

</template>

<script>

</script>
<style>
</style>
```

goto http://getbootstrap.com/examples/jumbotron-narrow/

add html
```html
<template>
<!--paste-->
<div class="header clearfix">
<nav>
<ul class="nav nav-pills pull-right">
<li role="presentation" class="active"><a href="#">Home</a></li>
<li role="presentation"><a href="#">About</a></li>
<li role="presentation"><a href="#">Contact</a></li>
</ul>
</nav>
<h3 class="text-muted">Project name</h3>
</div>
<!--paste-->
</template>

<script>

</script>
<style>
</style>
```

delete tag in **App.vue**

```
<template>
<div id="app">
<!--delete-->
<!--delete-->
</div>
</template>

<script>
export default {
//delete
}
</script>

<style>
//delete
</style>

```

go to **Navbar.vue**

```html
<template>
<div class="header clearfix">
<nav>
<ul class="nav nav-pills pull-right">
<li role="presentation" class="active"><a href="#">Home</a></li>
<li role="presentation"><a href="#">About</a></li>
<li role="presentation"><a href="#">Contact</a></li>
</ul>
</nav>
<h3 class="text-muted">Project name</h3>
</div>
</template>

<script>
///create component
</script>

<style>

</style>
```

import component in **App.vue** and add **style**

```javascript
<template>
<div id="app" class="container">
<my-navbar></my-navbar> <!--add code-->
</div>
</template>

<script>
import Navbar from './components/Navabarb.vue' //import navbar
export default {
//add
components : {
'my-navbar' : Navbar
}
//add
}
</script>
/* Space out content a bit */
body {
padding-top: 20px;
padding-bottom: 20px;
}

/* Everything but the jumbotron gets side spacing for mobile first views */
.header,
.marketing,
.footer {
padding-right: 15px;
padding-left: 15px;
}

/* Custom page header */
.header {
padding-bottom: 20px;
border-bottom: 1px solid #e5e5e5;
}
/* Make the masthead heading the same height as the navigation */
.header h3 {
margin-top: 0;
margin-bottom: 0;
line-height: 40px;
}

/* Custom page footer */
.footer {
padding-top: 19px;
color: #777;
border-top: 1px solid #e5e5e5;
}

/* Customize container */
@media (min-width: 768px) {
.container {
max-width: 730px;
}
}
.container-narrow > hr {
margin: 30px 0;
}

/* Main marketing message and sign up button */
.jumbotron {
text-align: center;
border-bottom: 1px solid #e5e5e5;
}
.jumbotron .btn {
padding: 14px 24px;
font-size: 21px;
}

/* Supporting marketing content */
.marketing {
margin: 40px 0;
}
.marketing p + h4 {
margin-top: 28px;
}

/* Responsive: Portrait tablets and up */
@media screen and (min-width: 768px) {
/* Remove the padding we set earlier */
.header,
.marketing,
.footer {
padding-right: 0;
padding-left: 0;
}
/* Space out the masthead */
.header {
margin-bottom: 30px;
}
/* Remove the bottom border on the jumbotron for visual effect */
.jumbotron {
border-bottom: 0;
}
} /* Space out content a bit */
body {
padding-top: 20px;
padding-bottom: 20px;
}

/* Everything but the jumbotron gets side spacing for mobile first views */
.header,
.marketing,
.footer {
padding-right: 15px;
padding-left: 15px;
}

/* Custom page header */
.header {
padding-bottom: 20px;
border-bottom: 1px solid #e5e5e5;
}
/* Make the masthead heading the same height as the navigation */
.header h3 {
margin-top: 0;
margin-bottom: 0;
line-height: 40px;
}

/* Custom page footer */
.footer {
padding-top: 19px;
color: #777;
border-top: 1px solid #e5e5e5;
}

/* Customize container */
@media (min-width: 768px) {
.container {
max-width: 730px;
}
}
.container-narrow > hr {
margin: 30px 0;
}

/* Main marketing message and sign up button */
.jumbotron {
text-align: center;
border-bottom: 1px solid #e5e5e5;
}
.jumbotron .btn {
padding: 14px 24px;
font-size: 21px;
}

/* Supporting marketing content */
.marketing {
margin: 40px 0;
}
.marketing p + h4 {
margin-top: 28px;
}

/* Responsive: Portrait tablets and up */
@media screen and (min-width: 768px) {
/* Remove the padding we set earlier */
.header,
.marketing,
.footer {
padding-right: 0;
padding-left: 0;
}
/* Space out the masthead */
.header {
margin-bottom: 30px;
}
/* Remove the bottom border on the jumbotron for visual effect */
.jumbotron {
border-bottom: 0;
}
}
<style>
</style>
```

# Vue 2.0 and Laravel 5.3 #6 Authentication & Devtools

create **authentication** folder in **components** and create file

-> **components/authentication/login.vue**

-> **components/authentication/register.vue**

add code

```html
<template>

</template>

<script>

</script>
<style>
</style>
```

go to **App.vue**

```html
<template>
<div id="app" class="container">
<my-navbar></my-navbar> <!--add code-->
<signin></signin>
</div>
</template>

<script>
import Navbar from './components/Navabarb.vue' //import navbar
import Login from './components/authentication/login.vue' //import login
export default {
//add
components : {
'my-navbar' : Navbar,
'login' : Login
}
//add
}
</script>

```

go to **login.vue** and add

```
<template>
<div class="row">
<div class="col-md-6 col-md-offset-3">
<div class="panel panel-default">
<div class="panel-body">
<div class="form-group">
<input type="email" v-model="email" class="form-control" placeholder="Email"><!-- v-model two way binding-->
</div>
<div class="form-group">
<input type="password" v-model="password" class="form-control" placeholder="password">
</div>
<button class="btn btn-succes pull-right">Login</button>
</div>
</div>
</div>
<!------------ add -------------->
<pre>
{{$data}}
</pre>
<!------------ add -------------->
</div>
</template>

<script>
export default {
data () {
return {
email : '',
password : ''
}
}
}
</script>
```

go to **register.vue** and add

```html
<template>
<div class="row">
<div class="col-md-6 col-md-offset-3">
<div class="panel panel-default">
<div class="panel-body">
<!------------ add -------------->
<div class="form-group">
<input type="name" v-model="name" class="form-control" placeholder="name"><!-- v-model two way binding-->
</div>
<!------------ add -------------->
<div class="form-group">
<input type="email" v-model="email" class="form-control" placeholder="Email"><!-- v-model two way binding-->
</div>
<div class="form-group">
<input type="password" v-model="password" class="form-control" placeholder="password">
</div>
<button class="btn btn-succes pull-right">Rgister</button> <!-- change register -->
</div>
</div>
</div>
<!------------ add -------------->
<pre>
{{$data}}
</pre>
<!------------ add -------------->
</div>
</template>

<script>
export default {
data () {
return {
email : '',
password : ''
}
}
}
</script>
```

go to **App.vue** some add

```html
<template>
<div id="app" class="container">
<my-navbar></my-navbar> <!--add code-->
<signin></signin>
<!------------ add -------------->
<register></register>
<!------------ add -------------->
</div>
</template>

<script>
import Navbar from './components/Navabarb.vue' //import navbar
import Login from './components/authentication/login.vue' //import login
//------- add
import Register from './components/authentication/register.vue' //import register
//------- add
export default {
components : {
'my-navbar' : Navbar,
'login' : Login
// add
, 'register' : Register
}
//add
}
</script>

```

# Vue 2.0 and Laravel 5.3 #7 Routing

go to console and run


```
$ npm install vue-router --save
```
in src create **routes.js **

-> **src/routes.js**

and add code

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
import Login from './components/authentication/login.vue'
Vue.use(VueRouter)

const router = new VueRouter({
routes : [
{
path : "/login",
component : Login
}
]
})

export default router
```



go to **main.js**

```javascript
import Vue from 'vue'
import App from './App.vue'

//--- add
import Router from './routes.js'
//--- add

new Vue({
el: '#app',
render: h => h(App)
//--- add
, router : Router
})

```

go to **App.vue**

```html
<template>
<div id="app" class="container">
<my-navbar></my-navbar>
<!--add code-->
<router-view></router-view>
<!--add code-->
<signin></signin>
<register></register>
</div>
</template>
```


goto path

```
localhost:8080/#/login
```

you can see 3 from

go to **App.vue** and delete

```html
<template>
<div id="app" class="container">
<my-navbar></my-navbar> <!--add code-->
<router-view></router-view>
<!------------ delete -------------->
<signin></signin>
<register></register>
<!------------ delete -------------->
</div>
</template>

<script>
import Navbar from './components/Navabarb.vue' //import navbar

//------- delete
import Login from './components/authentication/login.vue' //import login
import Register from './components/authentication/register.vue' //import register
//------- delete
export default {
components : {
'my-navbar' : Navbar,
//------- delete
'login' : Login ,
'register' : Register
//------- delete

}
}
</script>

```

go back now browser and then

go to **routes.js**

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
import Login from './components/authentication/login.vue'

//--- add
import Register from './components/authentication/register.vue'
//--- add
Vue.use(VueRouter)

const router = new VueRouter({
routes : [
{
path : "/login",
component : Login
}
//--- add
,
{
path : "/register",
component : Register
}
//--- add
]
})

export default router
```

go to browser

check path



```
localhost:8080/#/
//can not see anything

localhost:8080/#/login
//form login

localhost:8080/#/register
//form register
```

# Vue 2.0 and Laravel 5.3 #8 Vue Resource & CORS

go to laravel project install laravel project for vuejs

go to **laravel project**
-> **routes/api.php**

```
//--- add
//vuejs
Route::get('/test' , function (){
return response()->json([
'user' => [
'first_name' => 'ADD',
'last_name' => 'VV'
]
]);
});

```

go to path laravel

```
localhost:8000/api/test

you can see json
```


and then go to path vue project install vue-resource

```
$ npm install vue-resource --save
```

go to **main.js** in vue project


```javascript
import Vue from 'vue'
import App from './App.vue'
import Router from './routes.js'


//--- add
import VueResource from 'vue-resource'
Vue.use(VueResource)
//--- add



new Vue({
el: '#app',
render: h => h(App)
//--- add
, router : Router
})

```

go to **login.vue** and add

```
<template>
<div class="row">
<div class="col-md-6 col-md-offset-3">
<div class="panel panel-default">
<div class="panel-body">
<div class="form-group">
<input type="email" v-model="email" class="form-control" placeholder="Email"><!-- v-model two way binding-->
</div>
<div class="form-group">
<input type="password" v-model="password" class="form-control" placeholder="password">
</div>
<!-- add method @click -->
<button @click="test" class="btn btn-succes pull-right">Login</button>
<!-- add method @click -->

</div>
</div>
</div>

</div>
</template>

<script>
export default {
data () {
return {
email : '',
password : ''
}
//---add
,
methods: {
test (){
this.$http.get("http://localhost:8000/api/test") // ip laravel server
.then(function(response){
console.log(response)
})
}
}
//---add

}
</script>
```

go to browser and click login you can see error
and must be use **laravel-core**

-> https://github.com/barryvdh/laravel-cors

## Installation
```
$ composer require barryvdh/laravel-cors
```

Add the Cors\ServiceProvider to your **config/app.php ** providers array:

```
Barryvdh\Cors\ServiceProvider::class,

```

go to laravel project

-> **app/Providers/RouteServiceProvider.php**

```
protected function mapApiRoutes()
{
Route::group([
// change
'middleware' => ['api','cors'], //change #artdvp#
// change
//'middleware' => 'api',
'namespace' => $this->namespace,
'prefix' => 'api',
], function ($router) {
require base_path('routes/api.php');
});
}
```

and run command

```
php artisan vendor:publish --provider="Barryvdh\Cors\ServiceProvider"
```

go to laravel project **config/cors.php. **

```
'supportsCredentials' => false,
'allowedOrigins' => ['localhost:8080'], //#artdvp#vuejs# edit for allow web reqeust
'allowedHeaders' => ['*'],
'allowedMethods' => ['*'],
'exposedHeaders' => [],
'maxAge' => 0,
'hosts' => [],
```

go to browser clear console and click login
again you can see not error and then get json data from api server

# Vue 2.0 and Laravel 5.3 #9 Generating Access Tokens with Passport

setting database
go to file
-> **database/seeds/DatabaseSeeder.php**
```<?php

use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
/**
* Run the database seeds.
*
* @return void
*/
public function run()
{
// $this->call(UsersTableSeeder::class);
factory(\App\User::class,10)->create(); //add seeder
}
}

```

and go to console

```
php artisan migrate --seed
```

go to database you will see user in tables

# Installation

To get started, install Passport via the Composer package manager:
```
composer require laravel/passport
```
and go to app.php

```
//provider

/*
* Package Service Providers...
*/
'Intervention\Image\ImageServiceProvider',
Collective\Html\HtmlServiceProvider::class,

//vue and laravel #artdvp#
Barryvdh\Cors\ServiceProvider::class,
//--- add Laravel\Passport\PassportServiceProvider::class,
//https://github.com/barryvdh/laravel-cors

//

/*

```

run command migrate again

```
php artisan migrate

//
Migrated: 2016_06_01_000001_create_oauth_auth_codes_table
Migrated: 2016_06_01_000002_create_oauth_access_tokens_table
Migrated: 2016_06_01_000003_create_oauth_refresh_tokens_table
Migrated: 2016_06_01_000004_create_oauth_clients_table
Migrated: 2016_06_01_000005_create_oauth_personal_access_clients_table
```
run command install passport

```
php artisan passport:install

//token ganerate
Encryption keys generated successfully.
Personal access client created successfully.
Client ID: 1
Client Secret: d8OPBbDmZbwNKZKnX28TjvseMZGNY1j5bgzkkNh7
Password grant client created successfully.
Client ID: 2
Client Secret: aZUVQYRLfBXrnlGsJVWkUSstfmm9avnbKymNZpRW
```

go to **User.php**
```
use Illuminate\Notifications\Notifiable;
use Illuminate\Foundation\Auth\User as Authenticatable;
//---add #artdvp#
use Laravel\Passport\HasApiTokens;
//

class User extends Authenticatable
{
//hasapi token
use HasApiTokens,Notifiable;

```

go to path
-> **app/Provider/AuthServiceProvider.php**

```
<?php

namespace App\Providers;

use Illuminate\Support\Facades\Gate;
use Illuminate\Foundation\Support\Providers\AuthServiceProvider as ServiceProvider;
//--- add #artdvp
use Laravel\Passport\Passport;
//--- add #artdvp

class AuthServiceProvider extends ServiceProvider
{
/**
* The policy mappings for the application.
*
* @var array
*/
protected $policies = [
'App\Model' => 'App\Policies\ModelPolicy',
];

/**
* Register any authentication / authorization services.
*
* @return void
*/
public function boot()
{
$this->registerPolicies();

//
//--- add #artdvp
Passport::routes();
//--- add #artdvp
}
}

```

go to **config auth.php**

```
'guards' => [
'web' => [
'driver' => 'session',
'provider' => 'users',
],

'api' => [
//change -- add
'driver' => 'passport',
//'driver' => 'token',
'provider' => 'users',
],
],


```
check routes in command


```
php artisan routes:list
```



go to **app/Provider/AuthServiceProvider.php**

```
<?php

namespace App\Providers;

use Illuminate\Support\Facades\Gate;
use Illuminate\Foundation\Support\Providers\AuthServiceProvider as ServiceProvider;
//--- add #artdvp
use Laravel\Passport\Passport;
//--- add #artdvp

class AuthServiceProvider extends ServiceProvider
{
/**
* The policy mappings for the application.
*
* @var array
*/
protected $policies = [
'App\Model' => 'App\Policies\ModelPolicy',
];

/**
* Register any authentication / authorization services.
*
* @return void
*/
public function boot()
{
$this->registerPolicies();

//
//--- add #artdvp
Passport::routes();
//--- add #artdvp
}
}

```

go to vue project and change **log.vue**
```
<template>
<div class="row">
<div class="col-md-6 col-md-offset-3">
<div class="panel panel-default">
<div class="panel-body">
<div class="form-group">
<input type="email" v-model="email" class="form-control" placeholder="Email">
</div>
<div class="form-group">
<input type="password" v-model="password" class="form-control" placeholder="password">
</div>
<button @click="login" class="btn btn-succes pull-right">Login</button>
</div>
</div>
</div>
<!--<pre>
{{$data}}
</pre>-->
</div>
</template>

<script>
export default {

//Vue 2.0 and Laravel 5.3 #6 Authentication & Devtools
data () {
return {
email : '',
password : ''
}
},
//Vue 2.0 and Laravel 5.3 #6 Authentication & Devtools
//create method
methods : {
login (){
//--- add
//--- add for token

var data = {
client_id : 2,
client_secret : 'aZUVQYRLfBXrnlGsJVWkUSstfmm9avnbKymNZpRW',
grant_type : 'password',
username : this.email,
password : this.password
}
this.$http.post("http://localhost:8000/oauth/token" , data) //change get to post and change path to // oathu/token //add data after token
.then( response => [
console.log(response)
])
/*.then(function(response){
console.log(response)
})*/
}
}
}
</script>
```


go to login.vue


```
<template>
<div class="row">
<div class="col-md-6 col-md-offset-3">
<div class="panel panel-default">
<div class="panel-body">
<div class="form-group">
<input type="email" v-model="email" class="form-control" placeholder="Email">
</div>
<div class="form-group">
<input type="password" v-model="password" class="form-control" placeholder="password">
</div>
<button @click="login" class="btn btn-succes pull-right">Login</button>
</div>
</div>
</div>
<!--<pre>
{{$data}}
</pre>-->
</div>
</template>

<script>
export default {

//Vue 2.0 and Laravel 5.3 #6 Authentication & Devtools
data () {
return {
email : '',
password : ''
}
},
//Vue 2.0 and Laravel 5.3 #6 Authentication & Devtools
//create method
methods : {
//--- add
//--- add for token
login (){
var data = {
client_id : 2,
client_secret : 'aZUVQYRLfBXrnlGsJVWkUSstfmm9avnbKymNZpRW',
grant_type : 'password',
username : this.email,
password : this.password
}
this.$http.post("http://localhost:8000/oauth/token" , data) //change get to post and change path to // oathu/token //add data after token
.then( response => [
console.log(response)
])
/*.then(function(response){
console.log(response)
})*/
}
}
}
</script>
```
