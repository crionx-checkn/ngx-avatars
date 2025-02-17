## &lt;ngx-avatars&gt;
[![npm version](https://badge.fury.io/js/ngx-avatars.svg)](https://badge.fury.io/js/ngx-avatars.svg) 
[![npm](https://img.shields.io/npm/dt/ngx-avatars.svg)](https://www.npmjs.com/package/ngx-avatars) 
[![Build Status](https://travis-ci.com/Heatmanofurioso/ngx-avatars.svg?branch=master)](https://travis-ci.org/Heatmanofurioso/ngx-avatars)
[![Angular Style Guide](https://mgechev.github.io/angular2-style-guide/images/badge.svg)](https://angular.io/styleguide)
![size](https://img.shields.io/bundlephobia/minzip/ngx-avatars.svg)

## NPM Project
[ngx-avatars](https://www.npmjs.com/package/ngx-avatars)

## Warning
Do not confuse with [ngx-avatar](https://github.com/HaithemMosbahi/ngx-avatar) This project is it's spiritual successor, and all credit goes to HaithemMosbahi and his fellow contributors which 
will remain in this project's contributing list.

The intention of this project is to maintain and evolve the solution due to the original owner not working actively on it anymore.

## Description

A universal avatar component for Angular applications that fetches / generates avatar based on the information you have about the user. The component has a fallback system that if for example an invalid Facebook ID is used it will try google ID and so on.

You can use this component whether you have a single source or a multiple avatar sources. In this case the fallback system will fetch the first valid avatar.

Moreover, the component can shows name initials or simple value as avatar.

![Angular Avatar component preview](https://cdn.rawgit.com/HaithemMosbahi/ngx-avatar/0bac9072/demo.png)


 Supported avatar sources:

 * Facebook
 * Google
 * Twitter
 * Instagram
 * Vkontakte (VK)
 * Skype
 * Gravatar
 * GitHub
 * Custom image
 * name initials
 * value

 The fallback system uses the same order as the above source list, Facebook has the highest priority, if it fails, google source will be used, and so on.

 If you enjoy watching videos, check out this [tutorial](https://medium.com/letsboot/lets-play-with-ngx-avatar-ec585dc39161) on medium which explains how to use ngx-avatars in your angular application.
 
 Check out this [link](https://stackblitz.com/edit/ngx-avatar-demo) to play with ngx-avatars :grinning:

## Installation

Install avatar component using [Yarn](https://yarnpkg.com/):

```bash
$ yarn add ngx-avatars
```

or

```bash
$ npm install ngx-avatars --save
```

## Usage

1. Import AvatarModule:

Once you have installed ngx-avatars, you can import it in your `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { HttpClientModule } from '@angular/common/http';

import { AppComponent } from './app.component';

// Import your AvatarModule
import { AvatarModule } from 'ngx-avatars';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    // Specify AvatarModule as an import
    AvatarModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

- `HttpClientModule` is mandatory in order to fetch the avatar from external sources (Gravatar, Google, ...).

2. Start using it:

Once the AvatarModule is imported, you can start using the component in your Angular application:

```html
<ngx-avatars></ngx-avatars>
```
## Examples

```html
<ngx-avatars facebookId="1508319875"></ngx-avatars>
<ngx-avatars googleId="1508319875"></ngx-avatars>
<ngx-avatars twitterId="1508319875"></ngx-avatars>
<ngx-avatars instagramId="dccomics" size="70"></ngx-avatars>
<ngx-avatars skypeId="1508319875"></ngx-avatars>
<ngx-avatars gravatarId="adde9b2b981a8083cf084c63ad86f753"></ngx-avatars>
<ngx-avatars gravatarId="user@gmail.com"></ngx-avatars>
<ngx-avatars src="assets/avatar.jpg"></ngx-avatars>
<ngx-avatars name="John Doe"></ngx-avatars>
<ngx-avatars value="75%"></ngx-avatars>

<ngx-avatars facebookId="userFacebookID" skypeId="userSkypeID"
 googleId="google" name="Haithem Mosbahi" src="assets/avatar.jpg"
 value="28%"  twitterId="twitter"
 gravatarId="adde9b2b981a8083cf084c63ad86f753" 
 size="100" [round]="true">
</ngx-avatars>

```
Check out this [file](https://github.com/Heatmanofurioso/ngx-avatars/blob/master/demo/src/app/app.component.html) for more examples on how to use ngx-avatars in your application.

## Demo
Check out this [link](https://ngx-avatar-demo.stackblitz.io/) for a live demo.
Also, you can play with ngx-avatars using an online editor [here](https://ngx-avatars-demo.stackblitz.io) on stackblitz.

Moreover, the demo folder contains an application generated with angular cli that uses ngx-avatars component.

To run the demo application :
```bash
$ yarn install
$ ng serve
```



## Options

| Attribute        | Type       | Default   | Description                                                                                                                                                                              |
|------------------|------------|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `facebookId`     | *string*   | null      |                                                                                                                                                                                          | Facebook ID                                                                                            |
| `googleId`       | *string*   | null      |                                                                                                                                                                                          |  Google ID                                                                                             |
| `twitterId`      | *string*   | null      |                                                                                                                                                                                          | Twitter Handle                                                                                         |
| `instagramId`    | *string*   | null      |                                                                                                                                                                                          | Instagram Handle                                                                                       |
| `vkontakteId`    | *string*   | null      |                                                                                                                                                                                          | VK ID                                                                                                  |
| `skypeId`        | *string*   | null      |                                                                                                                                                                                          |  Skype ID                                                                                              |
| `gravatarId`     | *string*   | null      |                                                                                                                                                                                          | email or md5 email related to gravatar                                                                 |
| `githubId`       | *string*   | null      |                                                                                                                                                                                          | Github ID                                                                                              |
| `src`            | *string*   | null      |                                                                                                                                                                                          | Fallback image to use                                                                                  |
| `name`           | *string*   | null      |                                                                                                                                                                                          | Will be used to generate avatar based on the initials of the person                                    |
| `value`          | *string*   | null      |                                                                                                                                                                                          | Show a value as avatar                                                                                 |
| `initialsSize`   | *number*   | 0         | Restricts the size of initials - it goes along with the name property and can be used to fix the number of characters that will be displayed as initials. The `0` means no restrictions. |
| `bgColor`        | *string*   | random    | Give the background a fixed color with a hex like for example #FF0000                                                                                                                    |
| `fgColor`        | *string*   | #FFF      | Give the text a fixed color with a hex like for example #FF0000                                                                                                                          |
| `size`           | *number*   | 50        | Size of the avatar                                                                                                                                                                       |
| `textSizeRatio`  | *number*   | 3         | For text based avatars the size of the text as a fragment of size (size / textSizeRatio)                                                                                                 |
| `round`          | *boolean*  | true      | Round the avatar corners                                                                                                                                                                 |
| `cornerRadius`   | *number*   | 0         | Square avatars can have rounded corners using this property                                                                                                                              |
| `borderColor`    | *string*   | undefined | Add border with the given color. border's default style is '1px solid borderColor'                                                                                                       |
| `style`          | *object*   |           | Style that will be applied on the root element                                                                                                                                           |
| `clickOnAvatar`  | *Output*   |           | Fired when the avatar is clicked. The component emits the source object that has been used to fetch the avatar.                                                                          |
| `referrerpolicy` | *string*   | null      | Adds the noreferrer flag to the img tag.                                                                                                                                                 |

 The source object has the following properties:
 * sourceType : avatar source ( Facebook, twitter, etc)
 * sourceId : identifier of the user
 * getAvatar(size) : method to fetch user avatar from the current source

## Override Avatar Configuration
The avatar module provides the possibility of customizing the avatar component by overriding some of its options. For example, the avatar module comes with a set of default colors used to randomly fill the background color of the avatar. Thus, it's possible to change the default list of colors and to pass your own list.

All you need to do is to configure the AvatarModule by calling **forRoot** method. The forRoot method takes an AvatarConfig Object that contains the overridden options. 

AvatarConfig interface has two properties: 
  * **avatarColors:** allows the user to override the default avatar colors by providing a new set of colors
  * **sourcePriorityOrder:** allows the user to change the avatar source priority order. If you want the avatar component to look for user initials first, twitter before facebook or any order you want, this is can be done using the sourcePriorityOrder property

The following code shows an example on how to import the AvatarModule with your own source priority order. 
With the given order, the avatar component will look first for the custom avatar image and then for user initials and after that it will look the rest of sources.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { HttpClientModule } from "@angular/common/http";

import { AppComponent } from './app.component';
import { UserService } from "./user.service";
import { AvatarModule, AvatarSource } from 'ngx-avatars';

const avatarSourcesOrder = [AvatarSource.CUSTOM, AvatarSource.INITIALS];

@NgModule({
  declarations: [
    AppComponent  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    // import AvatarModule in your app with your own configuration
    AvatarModule.forRoot({
      sourcePriorityOrder: avatarSourcesOrder
    })
  ],
  providers: [UserService],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

Here's an example on how to import the AvatarModule with your own set of colors.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { UserService } from "./user.service";
import { AvatarModule } from "ngx-avatars";
import { HttpClientModule } from "@angular/common/http";

const avatarColors = ["#FFB6C1", "#2c3e50", "#95a5a6", "#f39c12", "#1abc9c"];

@NgModule({
  declarations: [
    AppComponent  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    // import AvatarModule in your app with your own configuration
    AvatarModule.forRoot({
      colors: avatarColors
    })
  ],
  providers: [UserService],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

 **Avatar Styling**

 In addition to the style attribute, ngx-avatar style can be customized using css classes. Thus, the generated code offers two css classes that can be overridden :
 * **avatar-container** : class that represents the avatar container - the host element. Styles in this class will be applied on the avatar whether is an image or text.
 * **avatar-content** : css class that represents the avatar element which is embedded inside the avatar-container.
 
 To overcome Angular's view encapsulation, you may need to use the /deep/ operator to target it. Here's an example that shows how to override ngx-avatars style : 
 
 ```html
   <ngx-avatars class="my-avatar" value="HM"> </ngx-avatars>
 ```
 Your css file might look like this 
 
 ```css
 .my-avatar /deep/ .avatar-content {
     background-color : red !important;
 }
 ```

## Release Notes & History
* 1.5.0: Migrate to Angular V15
* 1.4.0: Migrate to Angular V14
* 1.3.2: Add referrerpolicy configuration to img tag. Update dependencies. Remove codelyzer.
* 1.3.1: Update dependencies
* 1.3.0: Added ability to disable src cache.
* 1.2.1: Updated several dependencies. Update Angular minor version. Add Husky Git Hooks. Migrate from TSLint to ESLint
* 1.2.0: Migrate Angular to V13. Migrate RXJS to V7.4.0
* 1.1.3: Fix package versioning in release
* 1.1.2: Fixed build issues. 
* 1.1.1: Fix package versioning in release
* 1.1.0: Update Angular to V 12
* 1.0.2: Fix production build and publish to npm registry
* 1.0.1: Update dependencies and project structure
* 1.0.0: Initial migration from ngx-avatar


## Contributing

Contributions and all possible collaboration are welcome.

* Fork it!
* Create your feature branch: git checkout -b my-new-feature
* Commit your changes: git commit -am 'Add some feature'
* Push to the branch: git push origin my-new-feature
* Submit a pull request :D


# Testing

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 11.2.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## License

MIT © [Tiago Casinhas](mailto:tiago.gaspar.casinhas@gmail.com)
