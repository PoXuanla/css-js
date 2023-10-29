# Grid

## grid-template-columns

定義橫排的格數，可針對每格設置寬度。

```css
grid-template-columns: 60px 1fr; 
grid-template-columns: 60px 1fr 1fr;
grid-template-columns: repeat(3, minmax(0, 1fr))
grid-template-columns: repeat(auto-fill, minmax(100px, 1fr))
grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
```

#### fr

在設置 row 裡代表寬度單位，用途是佔用剩餘空間，若有多個 fr 則會均分剩餘空間。

### minmax()

定義元素的最小與最大寬度。

常見有 <mark style="background-color:red;">minmax(0, 1fr)</mark>，當父層寬度不足時最小為０，相反則會佔用剩餘空間。

### repeat

重複定義相同的格子寬度。

```css
grid-template-columns: 60px 60px 60px;

//可替換成
grid-template-columns: repeat(3, 60px);
```

#### 另外 repeat 常見的使用方式為：

1. repeat 第一個參數使用 auto-fill 或 auto-fit
2. 第二個參數使用 minmax( customMinSize, 1fr )

```css
grid-template-columns: repeat(auto-fill, minmax(100px, 1fr))
```

### auto-fill ＆auto-fit

<mark style="background-color:orange;">共同點</mark>

* 兩者在空間不足的情況下元素皆會是 min size，塞不下的元素就會換行
* 當空間增加但還不比一個元素的 min size 大時，行中的每個元素就會平均分配多的空間

<figure><img src="../.gitbook/assets/auto-fill.gif" alt=""><figcaption><p>動圖演示</p></figcaption></figure>

<mark style="background-color:orange;">差異點</mark>

* 一行的空間足以放下所有元素，多出來的空間分配機制不一樣

{% tabs %}
{% tab title="auto-fit" %}
元素會平均分配剩餘空間。
{% endtab %}

{% tab title="auto-fill" %}
元素會平均分配剩餘空間取 minSize 的餘數。
{% endtab %}
{% endtabs %}







## 參考資料

[A Deep Dive Into CSS Grid minmax()](https://ishadeed.com/article/css-grid-minmax/)
