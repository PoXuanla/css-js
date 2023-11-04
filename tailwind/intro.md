# Intro



#### Utility First CSS

ClassName 都是一個個的 css property

不像一般的寫法為 class 思考名稱再定義所需的 css

開發上更為快速但 HTML 會充滿了 class

```html
// Normal
<div class="card"></div>

// Tailwind
<div class="w-10 h-10 rounded-sm"></div>
```

### 輕量化

build 階段可透過 Purge Tree-Shaking 沒使用到的屬性，大大的減少 css file 的大小。
