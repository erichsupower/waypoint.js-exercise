# Waypoints


Waypoints 是一個 library，可以在滾動到元素時，輕鬆執行函數。

新手使用指南：[Getting Started](http://imakewebthings.com/waypoints/guides/getting-started)。

有關使用和自定義的更多詳細訊息，請閱讀完整的[官方文件](http://imakewebthings.com/waypoints/api/waypoint)。

```js
var waypoint = new Waypoint({
  element: document.getElementById('thing'),
  handler: function(direction) {
    alert('You have scrolled to a thing')
  }
})
```

## Getting Started

`lib/` 目錄包含 jQuery 和 Zepto 的版本，以及沒有使用任何框架的版本。只需要選擇適合的版本加入專案。

```html
<!- 使用jQuery框架的版本 ->
<script src="/path/to/jquery.waypoints.min.js"></script>

<!- 沒有使用任何框架的版本 ->
<script src="/path/to/noframework.waypoints.min.js"></script>

```


## A Basic Waypoint

在創建新 Waypoint 時，我們必須傳遞一個選取元素。您可以在此選取元素上設置許多屬性，但其中兩個屬性是必需的，`element` 和 `handler`。

```
var waypoint = new Waypoint({
  element: document.getElementById('basic-waypoint'),
  handler: function() {
    notify('Basic waypoint triggered')
  }
})
```

`element` 告訴 Waypoints 在滾動期間要觀察該元素的位置，而 `handler` 是當該元素的頂部到達 viewport 頂部時將觸發的函式。

[DEMO](./demo/waypoint-basic.html)

## Directions

觸發航點時，處理程序函式將傳遞 `direction` 參數。

```
var waypoint = new Waypoint({
  element: document.getElementById('direction-waypoint'),
  handler: function(direction) {
    notify('Direction: ' + direction)
  }
})
```

## Offsets

預設情況下，當元素頂部到達 viewport 頂部時，會觸發一個 waypoint。

以下範例是從元素頂部距離 viewport 頂部 20px 時觸發它。

```
var waypoint = new Waypoint({
  element: document.getElementById('px-offset-waypoint'),
  handler: function(direction) {
    notify('I am 20px from the top of the window')
  },
  offset: 20 
})
```

## this

`this` 關鍵字是對 Waypoint 實體的引用。使用此 `this` 來訪問 API 中的所有屬性和方法。

最有用的屬性之一是 `element`，即 Waypoint 的 DOM 元素。

```
var waypoint = new Waypoint({
  element: document.getElementById('element-waypoint'),
  handler: function(direction) {
    notify(this.element.id + ' triggers at ' + this.triggerPoint)
  },
  offset: '75%'
})
```

## 可使用在自定義區塊內
waypoint 也可偵測在區塊內的元素。

[DEMO](./demo/waypoint-context.html)

也可偵測區塊內水平移動的元素。

[DEMO](./demo/waypoint-horizontal.html)

## 偵測元素的高度

[DEMO](./demo/waypoint-height.html)

## 加入 CSS 屬性
為目前偵測的元素加入 CSS 行內樣式。

[DEMO](./demo/waypoint-animate.html)

## Shortcuts

除了正常的 Waypoints 腳本之外，還可以使用擴充功能，讓常見的 UI 方式更容易實現:

- [Infinite Scrolling](http://imakewebthings.com/waypoints/shortcuts/infinite-scroll)
- [Sticky Elements](http://imakewebthings.com/waypoints/shortcuts/sticky-elements)
- [Inview Detection](http://imakewebthings.com/waypoints/shortcuts/inview)

## API documentation

[API documentation](http://imakewebthings.com/waypoints/api/waypoint) 更多可用的所有選項、方法和屬性。