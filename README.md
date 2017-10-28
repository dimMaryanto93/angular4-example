# Belajar Angular4

Angular adalah JavaScript framework untuk membuat aplikasi berbasis *Single Page Application* (SPA), SPA atau Single Page Application itu kurang lebih intinya hanya punya 1 halaman saja yang ditampilkan oleh browser (client) meski di dalamnya memiliki banyak file `.html` tetapi dengan angular akan merender atau memanipulasi *Domain Object Model* DOM dalam HTML supaya menjadi 1 halaman saja.

## Perbedaan _the version of Angular_

- AngularJs = AngularJs adalah ditulis dengan `.js` Javascript based. AngularJs adalah versi pertama dari Angular yang ditulis dengan bahasa Javascript dengan extension `.js`. Untuk belajar Angular2 atau Angular4 tidak harus belajar angularJs dulu karena ada perbedaan konsep didalamnya tetapi klo sudah pernah menggunakan angularJs akan lebih baik hanya tinggal menyesuaikan saja.
- Angular2 = Angular adalah ditulis dengan `.ts` Typescript based. Typescript adalah superset of typescript atau istilahnya framework dari Javascript, Jadi AngularJs versi 2 ini atau Angular2 sebutannya dia untuk saat ini menggunakan bahasa Typescript sebagai primary languagenya. Karena typescript memiliki kesamaan dengan sintax Java, C++, .Net dll. Typescript ini berbada dengan Javascript di sisi konsep klo Javascript menggunakan konsep _first class function_ atau di bungkus dengan function sedangan untuk typescript dibungkus dengan _class based_ Object Oriented pada umumnya.
- Angular4 adalah Updated versi dari Angular2.

## Membuat project dengan Angular-CLI

Angular-CLI adalah tools untuk membuat project, generate component, generate page, generate pipe dan masih banyak lagi ya, jadi AngularCLI ini adalah tools berbasis commandline untuk memudahkan kita (developer) membuat web berbasis angular.

### Intallation NodeJS

Untuk menginstall AngularCLI kita butuh package managernya Javascript yaitu `NPM v.4.x or letter` dan `Node v.6.x or letter` di Ubuntu menggunakan perintah berikut:

```sh 
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs build-essential
```

Setelah install package `NodeJs` secara otomatis kita memiliki package `npm` nah sekaran coba cek versinya menggunakan perintah berikut:

```sh 
dimmaryanto93@Aspire-E5-473G:~$ node -v
v8.8.1 # << the node version is 8.8.1
``` 

dan versi dari npm version seperti berikut:

```sh 
dimmaryanto93@Aspire-E5-473G:~$ npm -v
5.5.1 # << the npm version is 5.5.1
```

### Installing `@angular/cli`

Untuk menginstall package `@angular/cli` direkomentasikan menggunakan package `node` dan `npm` terbaru karena saya disini saat ini (Oktober 2017) masih menggunakan Angular4 masih works fine....

Untuk install angularCLI di linux membutuhkan superuser untuk installnya seperti berikut:

```sh 
npm install -g typescript lite-server @angular/cli
```

## Membuat project dengan `@angular/cli`

Untuk membuat project dengan angularCLI bisa dengan menggunakan perintah:

```sh 
ng new angular4 #example used >> ng new [project-name]
```

## Structure directory of Angular4

### e2e folder

folder ini biasanya digunakan sebagai unit testing di angular 

```sh 
e2e/
├── app.e2e-spec.ts
├── app.po.ts
└── tsconfig.e2e.json

0 directories, 3 files
```

### node_modules folder

folder ini isinya adalah lib javascript yang dibuntuhkan oleh angular

```sh 
├── @angular
├── @types
├── @webpack
└── typescript
.
.
.
.
3190 directories, 22978 files
```

### src 

Di folder ini kita akan menulis halaman, service, component, pipe, dan lain-lain untuk membuat aplikasi angular

```sh 
src/
├── app
│   ├── app.component.css
│   ├── app.component.html
│   ├── app.component.spec.ts
│   ├── app.component.ts
│   └── app.module.ts
├── assets
├── environments
│   ├── environment.prod.ts
│   └── environment.ts
├── favicon.ico
├── index.html
├── main.ts
├── polyfills.ts
├── styles.css
├── test.ts
├── tsconfig.app.json
├── tsconfig.spec.json
└── typings.d.ts

3 directories, 16 files
```

### Other files 

```sh 
├── angular-cli.json
├── .editorconfig
├── karma.conf.js
├── package.json
├── package-lock.json
├── protractor.conf.js
├── README.md
├── tsconfig.json
└── tslint.json
```

## Setup Styling with bootstrap

Untuk menambahkan library bootstrap di project angular4 dengan template project via `@angular/cli`, saya mau tambahkan melalui `npm` yaitu seperti berikut

```sh 
npm install jquery bootstrap --save
```

Maka outpunya seperti berikut:

```sh 
dimmaryanto93@Aspire-E5-473G:~/Documents/angular4$ npm install jquery bootstrap --save
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.1.2 (node_modules/fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.1.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

+ bootstrap@3.3.7
+ jquery@3.2.1
added 116 packages in 26.785s
```

And then saya mau include `bootstrap` dan `jquery` ke project saya, dengan cara tambahkan di properti `styles` untuk stylesheet atau css dan `scripts` untuk javascript file di dalam file `.angular-cli.json` seperti berikut:

```js 
"apps": [
    {
      // add here *.css with relative path
      "styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.min.css",
        "../node_modules/bootstrap/dist/css/bootstrap-theme.min.css"
      ],
      // add here *.js with relative path
      "scripts": [
        "../node_modules/jquery/dist/jquery.min.js",
        "../node_modules/bootstrap/dist/js/bootstrap.min.js"
      ],
      
    }
  ]
```
