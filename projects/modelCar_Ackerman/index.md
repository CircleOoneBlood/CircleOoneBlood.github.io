# 智能温控系统 - 课程项目

## 项目概述
这是一个基于Arduino的智能温度控制系统，能够自动调节环境温度并实时监控。

## 3D设计
![3D模型截图](./assets/images/model.png)

*设计说明：外壳采用模块化设计，方便维护和扩展*

## 电路设计
![电路原理图](./assets/images/circuit.png)

## 代码展示
```cpp
// 主控制程序
#include <DHT.h>
#define DHTPIN 2
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float temp = dht.readTemperature();
  Serial.print("温度: ");
  Serial.print(temp);
  Serial.println("°C");
  delay(2000);
}