# Angular

## 繫結

### 內嵌繫結 (Interpolation)

### 屬性繫結 (Property Binding)

### 事件繫結 (Event Binding)

- \$event

  取得事件 dom 物件包含產生事件的物件

- \$event.target

  取得產產生事件的物件 dom

### 雙向繫結 (Two-way Binding)

### 範本參考變數 (Template reference variables)

- #變數名稱，例如 #demo

如果用在標籤等於是這個標籤的 Dom 物件

```
    //取得 button dom 物件
    <button #demo></button>
```

用在 Directiver 可以使用這個 component 下的屬性及方法

```
    //可以使用 titleComponent.ts 中的屬性及方法
    <app-title #demo></app-title>
```

## Angular 指令 (Directives)

### 元件型指令 (Component Directives)

- Component

### 屬性型指令 (Attribute Directives)

本身不會有自己的 Template

- ngModel
- NgStyle

```
    <h1 [ngStyle]="{'屬性(css style)': 值}"><h1>
    <h1 [ngStyle]="{'font-size: 20px}"><h1>
```

- NgClass

```
    <h1 [ngClass]="{'class': bool}"><h1>

    //html
    <h1 [ngClass]="{'highlight': true}"><h1>

    //css
    .highlight{
        background-color:red;
    }
```

### 結構型指令 (Structural Directives)

- NgIf

  bool 決定是否要顯示 div

```
    <div id="test1" *ngIf="bool"></div>
```

- NgSwitch

```
    <div [ngSwitch] = "bool">
        <div *ngSwitchCase="0"></div>
        <div *ngSwitchCase="1"></div>
        <div *ngSwitchDefault></div>
    </div>
```

透過 ng-container 可以讓結構型指令不會產生出額外的 HTML tag，套用 HTML 版型時也比較不容易出錯

```
    <ng-container [ngSwitch] = "bool">
        <ng-container *ngSwitchCase="0"></ng-container>
        <ng-container *ngSwitchCase="1"></ng-container>
        <ng-container *ngSwitchDefault></ng-container>
    </ng-container>
```

- NgFor

```

```

### 管線元件 (pipe component)

在使用內嵌繫結或屬性繫結時候可以將輸出丟到 pipe 元件後在輸出到畫面上

- UpperCase 轉大寫

```
    <a>{{item.title|uppercase}}</a>
```

- LowerCase 轉小寫

```
    <a>{{item.title|lowercase}}</a>
```

- Date
- Currency
- Percent

### 安全導覽運算子 (?.)

只能使用在 Templage 裡面，加上 ?. 幫助判斷要取的值是否為 undefined 或 null ，如果是直接 return null ，避免錯誤發生

```
    <a>{{item.title|lowercase}}</a>
```

### 避免範本中出現 TypeScript 型別錯誤

跳離 typeScript 檢查

- item['title]
- \$any()

```
     <a>{{$item['title']|lowercase}}</a>
     or
     <a>{{$any(item).title|lowercase}}</a>
```
