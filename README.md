# SharkFin Select Plus - 智能股票筛选系统

## 项目目标

SharkFin Select Plus是一个结合技术分析和人工智能的智能股票筛选系统，通过量化分析和技术指标筛选出最具投资价值的股票，帮助投资者发现潜在的投资机会。

## 功能特点

- 自动数据采集：使用akshare库获取A股市场市值前1000的公司数据
- 技术指标分析：计算多个技术分析指标（MA、RSI、MACD等）
- AI智能分析：使用DeepSeek LLM模型进行智能分析和评分
- 量化筛选：基于多维度指标进行股票筛选
- 自动报告生成：生成详细的分析报告和投资建议

## 技术指标

系统计算的技术指标包括：
- 移动平均线（MA5、MA10、MA20）
- 相对强弱指数（RSI）
- 布林带（BBANDS）
- MACD指标
- 随机指标（KDJ/STOCH）
- 平均真实波幅（ATR）
- 动量指标（MOM）
- 威廉指标（WILLR）
- 能量潮（OBV）
- 波动率（VOLATILITY）

## 技术栈

- 编程语言：Python 3.9+
- 主要库：
  - akshare：股票数据获取
  - TA-Lib：技术指标计算
  - pandas：数据处理
  - numpy：数值计算
  - openai：LLM接口调用
  - scikit-learn：机器学习算法

## 安装说明

1. 安装Python依赖：
```bash
pip install -r requirements.txt
```

2. 安装TA-Lib：
- Windows：从[这里](http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-msvc.zip)下载并安装
- Linux：`sudo apt-get install ta-lib`
- macOS：`brew install ta-lib`

或使用conda安装：
```bash
conda install -c conda-forge ta-lib
```

3. 配置LLM API：
在`LLM_API.txt`文件中填写API配置信息

## 使用说明

1. 数据采集：
```bash
python stock_data_crawler.py
```

2. 运行分析：
```bash
python main.py
```

3. 查看结果：
- 分析报告将保存在`report`目录下
- 筛选结果将保存在`data/top_10_stocks.csv`

## 输出示例

```
推荐的10支股票：
    代码    评分
0  600519  0.95
1  000858  0.93
2  600036  0.92
...
```

## 项目结构

- `main.py`: 主程序入口
- `model_processing.py`: AI模型处理模块
- `quantitative_analysis.py`: 量化分析模块
- `stock_data_crawler.py`: 数据采集模块
- `news_sentiment.py`: 新闻情感分析模块
- `db_init.py`: 数据库初始化
- `db_maintenance.py`: 数据库维护
- `utils.py`: 工具函数
- `config.py`: 配置文件
- `LLM_API.txt`: LLM API配置
- `data/`: 股票数据存储目录
- `report/`: 分析报告存储目录

## 注意事项

- 使用前请确保已正确配置API密钥
- 建议在非交易时段运行数据采集
- 系统生成的建议仅供参考，请结合实际情况进行投资决策
- 投资有风险，入市需谨慎

## 环境要求

- Python >= 3.9
- TA-Lib >= 0.4.0
- 其他依赖见requirements.txt
