# @ubirch/angularx-qrcode

**ATTENTION - This package will be removed soon - please use the original package [angularx-qrcode](https://www.npmjs.com/package/angularx-qrcode) again!!**

`@ubirch/angularx-qrcode` is a fast and easy-to-use Ionic 4/5 and Angular 12/13 QR Code component/module library to generate QR Codes (Quick Response)
in your Ionic and Angular app with support for AOT and the Ivy compiler and runtime.
It is a drop-in replacement for the no-longer-maintained `angularx-qrcode` package of Andreas Jacob (http://cordobo.com/)
which was a replacement for angular2 component `ng2-qrcode` and based on node-qrcode.

## Demo App

An Angular app with a working implementation of angularx-qrcode is available as a project in this repository. Run the command

```
ng serve demo-app
```

and open the url `http://localhost:4200/` in your browser

For versions prior to 12 use angularx-qrcode
[github.com/Cordobo/angularx-qrcode](https://github.com/Cordobo/angularx-qrcode).

## Install @ubirch/angularx-qrcode with Angular 13

The latest version of @ubirch/angularx-qrcode version works with Angular 13:

```
# Angular 13 and Ionic
npm install @ubirch/angularx-qrcode --save
```

## Install @ubirch/angularx-qrcode 12.0.x with Angular 12

Angular 12 requires @ubirch/angularx-qrcode version 12.0.0:

```
# Angular 12 and Ionic
npm install @ubirch/angularx-qrcode@12.0.0 --save
```

## Basic Usage

### Import the module and add it to your imports section in your main AppModule:

```
// File: app.module.ts
// all your imports
import { QRCodeModule } from 'angularx-qrcode';

@NgModule({
declarations: [
  AppComponent
],
imports: [
  QRCodeModule
],
providers: [],
bootstrap: [AppComponent]
})
export class AppModule { }
```

## Examples: How to implement angularx-qrcode

### Generate a QR Code from a string (directive only)

Now that Angular/Ionic knows about the new QR Code module,
let's invoke it from our template with a directive.
If we use a simple text-string, we need no additional
code in our controller.

```
<qrcode [qrdata]="'Your data string'" [width]="256" [errorCorrectionLevel]="'M'"></qrcode>
```

### Create a QR Code from a variable in your controller

In addition to our `<qrcode>`-directive in `example.html`,
lets add two lines of code to our controller `example.ts`.

```
// File: example.ts
export class QRCodeComponent {
  public myAngularxQrCode: string = null;
  constructor () {
    // assign a value
    this.myAngularxQrCode = 'Your QR code data string';
  }
}

// File: example.html
<qrcode [qrdata]="myAngularxQrCode" [width]="256" [errorCorrectionLevel]="'M'"></qrcode>
```

## Parameters

| Attribute            | Type    | Default     | Description                                                    |
| -------------------- | ------- | ----------- | -------------------------------------------------------------- |
| allowEmptyString     | Boolean | false       | Allow qrdata to be an empty string                             |
| colorDark            | String  | '#000000ff' | RGBA color, color of dark module                               |
| colorLight           | String  | '#ffffffff' | RGBA color, color of light module                              |
| cssClass             | String  | 'qrcode'    | CSS Class                                                      |
| elementType          | String  | 'canvas'    | 'canvas', 'svg', 'img', 'url' (alias for 'img')                |
| errorCorrectionLevel | String  | 'M'         | QR Correction level ('L', 'M', 'Q', 'H')                       |
| margin               | Number  | 4           | Define how much wide the quiet zone should be.                 |
| qrdata               | String  | ''          | String to encode                                               |
| scale                | Number  | 4           | Scale factor. A value of 1 means 1px per modules (black dots). |
| version              | Number  | (auto)      | 1-40                                                           |
| width                | Number  | 10          | Height/Width (any value)                                       |

## Note

Depending on the amount of data of the _qrdata_ to encode, a minimum _width_ is required.

## AOT - Ahead Of Time Compilation

`angularx-qrcode` supports AOT Compilation (Ahead-of-Time Compilation) which results in significant faster rendering. An AOT-enabled module is included. Further reading: https://angular.io/guide/aot-compiler

## Available commands

    # Build
    npm run build

## License

MIT License

Copyright (c) 2021 - present [Beate Fiss (UBIRCH.com)](http://ubirch.com/)
Copyright (c) 2018 - present [Andreas Jacob (Cordobo.com)](http://cordobo.com/)
