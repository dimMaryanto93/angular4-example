# Core of Angular4 :: Belajar Angular4

Ada beberapa di bab ini saya akan bahas tentang:

- Component
- Databinding
- Directive

## Component

Component adalah ...

## DataBinding

DataBinding bisa di bayangkan sebagai komunikasi, jadi magsudnya kita bisa terkoneksi antara property yang dibuat di component dengan yang view which is template.
DataBinding terdiri dari 

* String Interpolation
* Property Binding
* Two Way Binding

### String Interpolation

String Interpolation, konsep ini sama seperti pada teknologi web pada umumnya karena pada dasarnya hanya one way out jadi hanya fungsinnya menampilkan saja dari property di component ke view template. Contoh penggunaan String Interpolation seperti berikut:

Didalam sebuah component memiliki property `title` seperti berikut:

```ts 
/** 
 * component decorator & import angular/core
**/
export class AppComponent{
 title: string = 'Halo String Interpolation'; 
}
```

Nah di template or view, kita bisa menampilkan `value` dari property `title` tersebut dengan cara seperti berikut:

```html
<h3>{{title}}</h3>
``` 

Yaitu dengan menggunakan double qurlybracket ```{{namaProperty}}``` yang diikuti dengan menggunakan nama variable contohnya `title`.

### Property Binding

Jika String Interpolation hanya menampilkan saja, dengan Property Binding kita mengisi nilai dari view ke component ini artinya fitur sebaliknya dari String Interpolation. contohnya misalnya kita punya view (template) berupa html seperti berikut:

```html
<input type="text" name="judul" [ngModel]="title">
```

jadi Dari text inputan tersebut nilai yang di inputkan akan otomatis terisi ke property yang ada component dengan nama variable `title`. Property Binding ini ditandai dengan squarebrucket `[propertyName]` yang di assign ke suatu property di component.

### Two way Banding

Jadi Two way banding ini ada gabungan antara ke 2 binding sebelumnya yaitu String Interpolation dan Property Binding jadi intinya kita punya fitur masukan dan output. berikut cara penggunaanya:

```html
<input type="text" name="title" [(ngModel)]="title"> : value will be show here! when you input some text {{title}}
```

Kemudian kita deklarasi property di component dengan nama `title` seperti berikut:

```ts 
export class AppComponent{
 title: string = 'Halo String Interpolation'; 
}
```

Maka ketika awal di buka akan menampilkan `Halo Spring Interpolation` ketika text field ubah dan apa yang terjadi walll text pun ikut berubah karena fitur Two way Banding.

## Directive

Directive adalah ...

### Directive Build-in function

- `*ngFor`
- `*ngIf`
