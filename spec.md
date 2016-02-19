## 附件1
### 此規範包含三種格式如下

* 影片預覽
 * [Native Mobile In_Cover](https://goo.gl/k7cIZN)
 * [Native Mobile In_Read](https://goo.gl/hAIuEA)
 * [WebView Mobile In_Read](https://goo.gl/F3dL0t)

 
* 流程圖
 * [Native Mobile In_Cover](https://goo.gl/ij9WPi)
 * [Native Mobile In_Read](https://goo.gl/cAV6RT)
 * [WebView Mobile In_Read](https://goo.gl/QWNpw4)
 
* 細則
 * 程式版本請上傳至 github，甲方有讀取的權限。 
 * Native的部份 Layout用動態產生，Layout 再 new一個 Webview 用來載入外部Javascript，Javascript由甲方提供。
 * Webview 的部份因為可能需要用到開發端的 Webview 物件，希望對開發著最方便及穩定的方式開發，如: SDK 繼承開發端的 Webview 物件。
 * 三種格式都整合至同一個SDK。
 * SDK需測試能相容開發端 Objective-C 與 Swift 兩種程式。
 * 當進入附件2之測試階段時，需提供前端環境。
 * 程式變數命名規格需遵守camel case
 * 與Javascript 的接口參照「API 定義」

## API 定義
### 設定必要參數 (From Native)

`ONEAD_config(params:json string)`

```
{
    uid:"'1000033'", 
    guid:"uuu-aaa-bbb0-ddd", 
    network_status:"WIFI|3G", 
    play_mode:"mobile-app-incover|mobile-app-inread", 
    dedicated_pid:"12615", 
    is_native_view:"true|false", 
    ad_environment:"production|test"
}
```

### 影片暫停/續播 (From Native)

`ONEAD_videoState(params:string)`

```
//play | pause
```

### 通知頁面已載入 (From Javascript)

`ONEAD_BRIDGE_pageFinished,pageFinished(Boolean)`

```
//true | false
```

### 取得 volume 狀態 (From Javascript)

`ONEAD_BRIDGE_audioManager,audioManager()`

```
//不帶參數
```


### 影片點擊 (From Javascript)

`ONEAD_BRIDGE_videoClick,videoClick()`

```
//不帶參數
```

### 播放結束 (From Javascript)

`ONEAD_BRIDGE_videoEnd,videoEnd()`

```
//不帶參數
```

### 關閉WebViewAd (From Javascript)

`ONEAD_BRIDGE_closeAD,closeAD()`

```
//不帶參數
```

### 取得BannerUrl (From Javascript)

`ONEAD_BRIDGE_clickURL,clickURL(String url)`

```
//string 類型 URL 參數
```
