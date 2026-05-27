# 蝦蟇賭場：High / Low

這是一個可直接放到 GitHub Pages 的單頁小遊戲。

## 檔案結構

```text
.
├── index.html
└── README.md
```

目前角色圖片與牌面圖片使用 `static.wixstatic.com` 圖片網址，因此不需要額外上傳圖片檔就能運作。

## 上傳到 GitHub Pages

1. 在 GitHub 建立一個新的 repository。
2. 將 `index.html` 與 `README.md` 上傳到 repository 根目錄。
3. 進入 repository 的 **Settings**。
4. 找到 **Pages**。
5. Source 選擇 **Deploy from a branch**。
6. Branch 選擇 `main`，資料夾選擇 `/root`。
7. 儲存後等待 GitHub Pages 產生網址。

通常網址會像這樣：

```text
https://你的帳號.github.io/你的repository名稱/
```

## 修改背景圖片

預設頁面底色是黑色。

如果想放背景圖片，可以在 `index.html` 裡找到這段：

```css
:root {
  --page-bg-color: #000000;
  --page-bg-image: none;
}
```

改成：

```css
:root {
  --page-bg-color: #000000;
  --page-bg-image: url("./images/background.png");
}
```

接著在 GitHub 裡新增 `images` 資料夾，並把背景圖命名為：

```text
background.png
```

如果想用外部圖片網址，也可以寫成：

```css
--page-bg-image: url("https://example.com/background.png");
```

## 修改角色圖片

在 `index.html` 裡搜尋：

```js
const NPC_IMAGES = {
```

可以替換十三號不同狀態的圖片網址。

## 修改牌面圖片

在 `index.html` 裡搜尋：

```js
const CARD_IMAGES = {
```

可以替換 2 到 Q 與特殊牌的圖片網址。

## 注意事項

最高連勝會使用瀏覽器的 `localStorage` 儲存。不同裝置、不同瀏覽器會各自保存紀錄。
