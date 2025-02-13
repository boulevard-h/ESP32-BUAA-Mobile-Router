
# WiFi STA-AP中继器（支持校园网WPA2-ENT PEAP认证）

修改自esp-idf官方demo: https://github.com/espressif/esp-idf/tree/release/v5.4/examples/wifi/softap_sta，添加校园网常用的WPA2-ENT PEAP认证方式。

esp-idf版本：v5.4

## 配置

在`main/config.h.tmp`中配置STA和AP，重命名为`config.h`：
- STA_WIFI_SSID 为校园网SSID
- STA_EAP_USERNAME 校园网账户名
- STA_EAP_PASSWORD 校园网密码
- STA_MAXIMUM_RETRY 连接失败后的最大尝试次数
- AP_WIFI_SSID ESP32 创建的WiFi名
- AP_WIFI_PASSWORD ESP32 创建的WiFi密码
- AP_MAX_CONNECTIONS 最大连接数
- AP_WIFI_CHANNEL 信道

编译前运行`idf.py menuconfig`，确保打开 Component config -> LWIP 下的 Enable copy between Layer2 and Layer3 packets, Enable IP forwarding, Enable NAT 选项。