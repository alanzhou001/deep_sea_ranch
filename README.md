# 深海牧场

## 任务背景

本子任务致力于探讨深海甲烷喷发与海洋生物分布之间的关系，并基于多源视频、图像和化学数据进行建模与分析。本任务的母项目是一个多学科交叉研究项目，结合了计算机视觉、生态学、地理信息系统（GIS）、化学分析与生态建模技术。本研究的主要目标是量化甲烷喷发对海底生物群落的影响，并探索喷发规模与生物分布、物种多样性之间的关系。

### 数据来源

项目数据来源于深潜器的多视角摄像系统以及海水化学与微生物的垂直采样。我们收集了来自深潜器的以下视频数据：

- **前置摄像头**
- **尾端摄像头**
- **左右两个侧翼摄像头**

此外，还进行了竖直方向的海水化学与微生物数据采样，这些数据将用于分析甲烷喷发对不同海水层的化学影响和微生物分布。

## 项目目标

1. **海底景观重建**：根据多角度视频数据合成完整的海底二维图景，进行海底景观的复现，构建海底环境的整体视觉图。
2. **海底生物分布分析**：基于深潜器传回的视频，分析海底特定位置的生物密度和数量，探索海底不同生物群体在空间上的分布模式。
3. **甲烷喷发与生物分布关系分析**：量化甲烷喷发量与周围生物分布和密度的关系，并通过生态系统建模技术，预测甲烷喷发对生物分布的长期影响。
4. **海水化学与微生物分布分析**：基于海水采样数据，分析甲烷喷发对海水化学和微生物分布的影响，构建甲烷喷发影响范围的预测模型。

## 任务分配

### 1. 海底景观重建组

- **目标**：使用计算机视觉与图像处理技术，对来自不同视角的海底视频进行图像拼接和重构，合成完整的海底景观图。
- **技术要点**：目标检测、图像配准与拼接、三维建模、点云分析。
- **关键技术**：OpenCV, SIFT/SURF 特征匹配, 点云处理（PCL），深度学习模型（如 YOLO, Mask R-CNN）。

### 2. 海底生物分布统计分析组

- **目标**：使用机器学习算法自动识别和统计海底特定区域内的生物种类和密度，并分析其时空分布特征。
- **技术要点**：目标检测、图像识别、数据标注与分类、统计分析。
- **关键技术**：深度学习（TensorFlow, PyTorch），图像标注工具（如 LabelMe），数据可视化（Matplotlib, Seaborn）。

### 3. 甲烷喷发与生物分布关系分析组

- **目标**：构建甲烷喷发对海洋生态系统中生物分布影响的模型，并量化甲烷喷发量与生物密度、种群数量之间的关系。
- **任务描述**：
  1. 通过分析甲烷喷发区域与非喷发区域的生物数量差异，探讨甲烷喷发对局部生态系统的直接影响。
  2. 构建甲烷喷发量与生物数量之间的关系模型，并进行时空预测。
  3. 探讨甲烷喷发量、频率对生物聚集模式的长期影响。
- **技术要点**：生态系统建模、物种分布模型（SDM）、广义线性模型（GLM）、时空分析、机器学习。
- **关键技术**：scikit-learn, statsmodels, PyGAM, PyKrige, GeoPandas。

### 4. 海水化学与微生物分布分析组（**当前任务**）

- **目标**：基于海水垂直采样数据，量化甲烷喷发对不同深度海水化学成分和微生物群落的影响，构建甲烷扩散模型。
- **技术要点**：空间数据处理、垂直采样数据分析、空间自相关与插值分析。
- **关键技术**：GeoPandas, Rasterio, PyProj, Kriging 插值（PyKrige）。

## 当前子任务：甲烷喷发与生物分布关系分析

### 任务说明

- 本子任务的目标是使用生态系统建模技术来理解甲烷喷发对海洋生态系统中生物分布的影响，量化甲烷浓度与生物数量之间的关系。
- 当前阶段主要聚焦于：
  1. 建立甲烷浓度与生物分布的基础数据集。
  2. 使用回归模型（如 GLM）和机器学习模型（如 Random Forest）进行关系量化。
  3. 根据历史喷发数据，探索甲烷喷发量对物种分布的预测模型。

### 使用技术栈

- **数据处理**：`pandas`, `numpy`
- **数据分析与统计**：`scipy`, `statsmodels`
- **生态系统建模与预测**：`scikit-learn`, `pyGAM`
- **地理空间数据分析**：`GeoPandas`, `PyKrige`
- **可视化**：`matplotlib`, `seaborn`
- **待更新**：

### 各文件夹和文件说明

- **`data/`**：用于存放数据文件。
- **`notebooks/`**：用于保存 Jupyter Notebook 文件。
- **`scripts/`**：包含多个 Python 脚本，用于处理数据、进行特征工程和模型训练等任务。
- **`models/`**：用于存放训练后的机器学习模型和生态模型，并包含参考文献和研究论文。
- **`references/`**：保存相关的参考文献（如模型说明文档、参考手册）。
- **`article/`**：保存研究论文。
- **`environment.yml`**：用于虚拟环境的配置文件，便于复现项目的开发环境。
- **`README.md`**：项目说明文件，包含项目背景、目标、技术细节和环境配置说明。

## 进度

1. **创建虚拟环境：**
   - 2024/10/03
   - 主要使用python语言
   - 相关依赖库见environment.yml
   - env_name:deepsea

2. **尝试使用yolo识别气泡：**
   - 2024/10/15
   - 人工标注训练集工作难度大，效果不佳，将部署sam模型尝试实现自动标注

## 贡献与交流

本项目属于团队合作项目，欢迎团队成员对不同任务模块进行补充、改进或提出新的研究思路。如果对当前任务有任何建议或需要交流，请通过以下方式联系本人：

- 姓名： 周陈序
- 联系邮箱：[alanzhou@sjtu.edu.cn]
- 微信：sx12345678zcx

## 更新记录

- 23:18,2024/10/03:创建项目及此文档，进行首次虚拟环境配置和调试，初步探索未来方向
- 22:00，2024/10/15:尝试使用yolo识别气泡
- 22:00,2024/10/20:第一次小组会议，沟通进度，交流想法，确定下一步方向
- 待续
