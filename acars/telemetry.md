# ACARS 遥测规范

ACARS 持续上传位置、速度、姿态、燃油、飞行阶段和模拟器状态，服务端将采样保存为 PIREP 的客观证据。

## 主要字段

| 字段 | 说明 |
|---|---|
| `capturedAt` | 采样时间 |
| `phase` | 飞行阶段 |
| `latitude`, `longitude` | 经纬度 |
| `altitude`, `altitudeAboveGround` | 高度和离地高度 |
| `groundSpeed`, `indicatedAirSpeed` | 地速和指示空速 |
| `verticalSpeed` | 垂直速度 |
| `pitch`, `bank`, `gForce` | 姿态与载荷 |
| `paused`, `slew`, `stall`, `crashed` | 异常状态 |

## 遥测质量

采样间隔超过配置阈值会形成遥测中断。位置跳变、Slew 和着陆率缺失会降低数据可信度，并可能阻止自动通过。
