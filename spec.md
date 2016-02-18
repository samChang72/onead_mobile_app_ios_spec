## 附件1
### 此規範包含三種格式如下

* 影片預覽
 * Native Mobile In_Cover:https://goo.gl/NnXc83
 * Native Mobile In_Read:https://goo.gl/h2GomA
 * WebView Mobile In_Read:https://goo.gl/wOqCPX
 
* 流程圖
 * Native Mobile In_Cover:https://goo.gl/ij9WPi
 * Native Mobile In_Read:https://goo.gl/cAV6RT
 * WebView Mobile In_Read:https://goo.gl/QWNpw4
 
* 細則
 * 程式版本請上傳至 github，甲方有讀取的權限。 
 * Native的部份 Layout用動態產生，Layout 再 new一個 Webview 用來載入外部Javascript，Javascript由甲方提供。
 * Webview的部份因為可能需要用到開發端的 Webview 物件，希望對開發著最方便及穩定的方式開發，如: SDK 繼承開發端的webview物件。
 * 三種格式都整合至同一個SDK。
 * SDK需測試能相容開發端 Objective-C 與 Swift 兩種程式。
 
* Javascrpit 與 Webview 的 互動接口

| Function  | Caller  |API name   | 說明 |
|---|---|---|---|
|  設定必要參數 |Native   |ONEAD_config(params:jason string)|jasonObject,{uid:"'1000033'",guid:"uuu-aaa-bbb0-ddd",network_status:"wifi",play_mode:"mobile-app-incover",dedicated_pid:"12615",is_native_view:"true",ad_environment:"production"}  常數值:<br>play_mode = "mobile-app-incover" or "mobile-app-inread"<br>is_native_view=boolean<br>ad_environment= "production" or "test"<br>network_status="WIFI" or "3G"...etc |
| 影片暫停/續播  | Native  | ONEAD_videoState(params:string) | 常數值: <br> "play" or "pause" |
|  通知頁面已載入 |Javascript    |  ONEAD_BRIDGE_pageFinished |Javascript 會帶boolean參數，true有查到廣告，false沒有 |
| 取得 volume 狀態  |Javascript    |  ONEAD_BRIDGE_audioManager |不帶參數 |
| 影片點擊  |Javascript    |  ONEAD_BRIDGE_videoClick |不帶參數 |
|  播放結束 |Javascript    |  ONEAD_BRIDGE_videoEnd |不帶參數 |
|  關閉WebViewAd |Javascript    |  ONEAD_BRIDGE_closeAD |不帶參數 |
| 取得BannerUrl  |Javascript    |  ONEAD_BRIDGE_clickURL |Javascript 會帶 string 類型 URL 參數 |


