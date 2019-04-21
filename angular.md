# Angular

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
