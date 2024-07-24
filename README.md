
# ESPHome培正本地计算谷峰电价，本代码教程主要融合论坛大佬的教程Esphome-Pzem004T-Electricity-Calculation

相关分支介绍
mqtt-rtc：mqtt版本的esphome配置带rtc时钟同时兼容ESPhome的Api，相关开发板使用的是合宙系列esp32c3，如果要相关型号请直接修改esp32c3.yaml，Esphome版本 2024.7.0 Documentation

如果需要移植，Esphome培正电表谷峰计量本地计算-mqtt通信-带rtc时钟.yaml，请完善yaml【需要修改】，本配置按照上海谷峰电价，5人用电标准实施


float all_prices[3][2] = { {0.617, 0.307}, {0.677, 0.337}, {0.977, 0.487} };
float total_usage = id(actual_annual_usage).state; //标准电费。5人以上用电阶梯加1200度.普通3120-4800 5人4320-6000
if(total_usage <= 4320) step_id=0;
if((total_usage>4320) && (total_usage <= 6000)) step_id=1;
if(total_usage > 6000) step_id=2;
id(global_step_id) = step_id;

## 贡献

我们随时欢迎大家的贡献!

请参阅 `contributing.md` 了解如何开始贡献。

请遵守本项目的 `行为准则`。

