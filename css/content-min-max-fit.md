# content(min、max、fit)

## max-content

完整顯示元素文字內容，不會因為 container 空間不夠而壓縮。

#### 示例一、在 container 空間足夠的情況：

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.39.22.png" alt=""><figcaption></figcaption></figure>

#### 示例二、在 container 空間不夠的情況：

仍然會完整顯示，不過會超出 container 的寬度。

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.38.39.png" alt=""><figcaption></figcaption></figure>

## min-content

以最小寬度呈現文字內容。

#### 示例一、在 container 空間足夠的情況：

遇到空白符會斷行，基本以最長的單字為元素寬度。

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.43.36.png" alt=""><figcaption></figcaption></figure>

#### 示例二、在 container  空間不夠的情況：

已經縮到最小了，會超出去很正常。

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.47.56.png" alt=""><figcaption></figcaption></figure>



## fit-content

在 container 空間足夠的情況以 <mark style="background-color:orange;">max-content</mark> 顯示，

若空間不夠則以接近 <mark style="background-color:orange;">min-content</mark> 顯示，詳細請看示例二。

#### 示例一、在 container 空間足夠的情況：

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.54.29.png" alt=""><figcaption></figcaption></figure>

#### 示例二、在 container 空間不夠的情況：

參照下面兩張圖，<mark style="background-color:orange;">fit-content</mark> 在空間不夠的情況下內容會逐漸換行，而非像 <mark style="background-color:orange;">min-content</mark> 一次就把內容縮到最小。

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.55.59.png" alt=""><figcaption><p>空間已容不下最後一個單字，因此換行顯示。</p></figcaption></figure>

<figure><img src="../.gitbook/assets/截圖 2023-10-27 21.57.13.png" alt=""><figcaption><p>空間進一步壓縮，因此倒數第二個單詞也換行。</p></figcaption></figure>

## 參考資料

[CSS 寬度自適應](https://shinyu0430.github.io/2021/09/21/maxwidthminwidthfitcontent/)
