# MFE5210assignment
## 项目概述
该项目使用 Python 进行股票因子策略的回测，涵盖动量、均值回归、波动率、成交量突增和 RSI 五种常见因子。通过对 20 只股票的因子信号进行回测，计算每个因子的夏普比率，并生成累积盈亏曲线和因子相关性热力图，帮助分析各因子在不同市场条件下的表现。

### 1. 数据下载
该脚本从 Yahoo Finance 下载指定股票的历史数据，包括收盘价格（Adj Close）和成交量（Volume）。可用于回测的数据集包含以下股票：
AAPL\MSFT\GOOGL\AMZN\META\NVDA\TSLA\BRK-B\JPM\JNJ\V\PG\XOM\UNH\HD\MA\BAC\PFE\ADBE\KO

### 2. 因子计算:
为每只股票计算以下因子：
- Momentum（动量因子）：基于过去 20 天的收益计算动量因子。
- MeanReversion（均值回归因子）：基于过去 20 天的价格，计算均值回归因子。
- Volatility（波动率因子）：基于价格变化的标准差计算波动率因子。
- VolumeSpike（成交量突增因子）：基于成交量变化的平均值计算成交量突增因子。
- RSI（相对强弱指数）：计算 14 天的相对强弱指数（RSI）。

### 3. 因子信号生成
基于因子值的排名，生成做多（Top 30%）和做空（Bottom 30%）的信号：
- 做多：选择因子排名前 30% 的股票。
- 做空：选择因子排名后 30% 的股票。

### 4. 回测策略
根据每个因子的信号生成相应的回测策略，并计算每日盈亏（PNL）。绘制策略的累积盈亏曲线（Equity Curve）。

### 5. 夏普比率计算
每个因子策略的夏普比率（Sharpe Ratio）被计算并输出，帮助评估因子策略的风险调整后收益。

### 6. 结果输出
	•	夏普比率：每个因子的夏普比率被保存到 sharpe_ratios.csv 文件中。
	•	因子数据：包含因子值的详细数据被保存到 alpha_factors_stacked.csv 文件中。
	•	PNL系列：每个因子的每日PNL被单独保存到文件。
	•	因子相关矩阵：输出所有因子之间的相关矩阵，并绘制相关矩阵热力图。

### 7. 图形展示
	•	累积盈亏曲线：为每个因子策略生成累积盈亏曲线。
	•	因子相关矩阵热力图：展示因子之间的相关性，帮助评估因子之间的关系。

<img width="681" alt="image" src="https://github.com/user-attachments/assets/741bb239-eded-4685-a996-3fb34e1dd883" />


--- Processing Factor: Momentum ---
- Factor Momentum - Long signals count: 4392
- Factor Momentum - Short signals count: 3660
- Factor Momentum - Mean Daily PNL: 0.000301, Std Dev Daily PNL: 0.015915
- Factor Momentum - Calculated Sharpe Ratio: 0.3004
<img width="1001" alt="image" src="https://github.com/user-attachments/assets/3d3b4f35-c1a2-4f83-b180-1d92078b9f11" />

--- Processing Factor: MeanReversion ---
- Factor MeanReversion - Long signals count: 4392
- Factor MeanReversion - Short signals count: 3660
- Factor MeanReversion - Mean Daily PNL: -0.000764, Std Dev Daily PNL: 0.014208
- Factor MeanReversion - Calculated Sharpe Ratio: -0.8539
<img width="1024" alt="image" src="https://github.com/user-attachments/assets/33be9c76-33fc-413c-97b9-d9ea94ddaf02" />

--- Processing Factor: Volatility ---
- Factor Volatility - Long signals count: 4392
- Factor Volatility - Short signals count: 3660
- Factor Volatility - Mean Daily PNL: 0.000984, Std Dev Daily PNL: 0.017602
- Factor Volatility - Calculated Sharpe Ratio: 0.8879

<img width="1011" alt="image" src="https://github.com/user-attachments/assets/cb9011fd-f9bd-49b8-9171-153f5b8eae9a" />

--- Processing Factor: VolumeSpike ---
- Factor VolumeSpike - Long signals count: 4392
- Factor VolumeSpike - Short signals count: 3660
- Factor VolumeSpike - Mean Daily PNL: -0.000138, Std Dev Daily PNL: 0.012307
- Factor VolumeSpike - Calculated Sharpe Ratio: -0.1780

 ![image](https://github.com/user-attachments/assets/d18756e4-f444-4f8b-9daa-aafbd20bbba7)
 
--- Processing Factor: RSI ---
- Factor RSI - Long signals count: 4392
- Factor RSI - Short signals count: 3660
- Factor RSI - Mean Daily PNL: 0.000876, Std Dev Daily PNL: 0.014606
- Factor RSI - Calculated Sharpe Ratio: 0.9524

<img width="1006" alt="image" src="https://github.com/user-attachments/assets/fa5a807e-af9e-4bfe-9e4c-3964ff5ebd9c" />


<img width="885" alt="image" src="https://github.com/user-attachments/assets/6300703f-1815-473b-8224-b9d26a91ec06" />

