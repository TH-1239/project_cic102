#cic102
# wireshark過濾封包指令
#akwejfui3q4bfgihq34gft87q3gh4orgofq3g4:

| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| 等於      |eq        | ==       |
| 不等於      |ne        | !=       |
| 大於      |gt        |>       |
| 等於      |it        | <      |


!arp and !nbns

ip.addr == 192.168.2.1
tcp.port == 443 or tcp.port == 80
# tcp.dstport == 80 and tcp.len>554

這串指令是一個用於過濾 TCP 封包的過濾器，常見於網路分析工具如 Wireshark。以下是各部分的解釋：

指令解釋
tcp.dstport == 80：

這部分指的是目標 TCP 端口（destination port）等於 80，通常表示 HTTP 流量。端口 80 是用於網頁伺服器的標準端口。
and：

這是一個邏輯運算符，用於將兩個條件結合起來，表示必須同時滿足這兩個條件。
tcp.len > 554：

這部分表示 TCP 封包的長度（tcp.len）必須大於 554 字節。這通常用來過濾出較大的封包，例如 HTTP 響應或數據傳輸，排除小的控制封包或開頭的封包。
總結
整體來看，這串指令用於過濾出目標端口為 80 且封包長度大於 554 字節的 TCP 流量，這可能是用於分析較大的 HTTP 請求或響應。這對於網絡故障排除和流量分析非常有用。
