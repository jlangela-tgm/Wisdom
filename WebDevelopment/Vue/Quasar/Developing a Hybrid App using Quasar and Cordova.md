# Developing a Hybrid App using Quasar and Cordova

In the following tutorial I will explain how to build an app using the Vue.js Framework Quasar in combination with Cordova to build an App that works on Android and iOS.

## Getting Started

First you need to have Quasar and Cordova installed 

````powershell
npm install -g @quasar/cli
````

To create A project use 

````shell
quasar create <folder_name>
````

You will now have to enter the Projects name and other information.
Now you are all setup with a starter Project

## Layout

in your `layouts` Folder you will find the `MainLayout.vue` File. This is your apps main layout which contains the different pages content. The Layout stays the same across pages but the content changes. The Pages content is added using the `<router-view>` Tag

```html
<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
    	<!-- Code Omitted -->
    </q-header>

    <q-drawer>
    	<!-- Code Omitted -->
    </q-drawer>

    <q-page-container>
      
      <router-view />

    </q-page-container>
  </q-layout>
</template>
```

To change the displayed page we use the `to=/...` attribute inside of a tag.

````html
<q-item
	to="/"
    exact
    clickable
    v-ripple>
    Page
</q-item>
````

In order to navigate between Pages you will need to setup routes

## Routes

inside of your `routes` folder open the `routes.js` file and add routes to your pages into the routes object

````javascript
const routes = [
  {
    path: '/',
    component: () => import('layouts/MainLayout.vue'),
    children: [
      { path: '/', component: () => import('pages/Root.vue') },
      { path: '/pageone', component: () => import('pages/Pageone.vue') }//Added Route
    ]
  }
]
````

