# IntelFiancialFraudDetection

### 分析报告见
![报告](https://github.com/Huangzisu/IntelFiancialFraudDetection/blob/master/%E5%88%86%E6%9E%90%E6%8A%A5%E5%91%8A.pdf)
### 项目汇总ppt见
![汇总ppt](https://github.com/Huangzisu/IntelFiancialFraudDetection/blob/master/Intel%E9%87%91%E8%9E%8D%E6%AC%BA%E8%AF%88%E6%A3%80%E6%B5%8B%E6%B1%87%E6%8A%A5.pptx)
### 所有源代码见
![code](https://github.com/Huangzisu/IntelFiancialFraudDetection/tree/master/code)

注：由于数据集文件过大无法上传，可以通过源代码中预处理方法以及分析报告中对应模型与数据集性能的分析来复现

---
## 团队名称
**HSY**

## 问题陈述
随着金融交易的不断增加，欺诈行为也在不断演变，对于金融机构而言，如何高效地检测和防范欺诈成为一项重要的任务。本团队致力于构建一个高效的金融欺诈检测模型，通过机器学习和数据分析技术，提高欺诈交易的检测准确性。

## 项目简介
本项目使用了多种机器学习算法，包括梯度提升 XG Boost、逻辑回归、人工神经网络等，以及相关的数据预处理和特征工程方法。我们主要关注不平衡数据集的处理，采用了过采样（SMOTE）、下采样（Random Under Sampler）、组合采样（Combined Sampling）等方法，以解决数据不平衡的问题，提高模型对欺诈行为的检测能力。同时我们还测试了不同模型的权重参数对于不平衡数据的作用，试图找出效果最好的解决方案。

## 构建项目时采用的技术栈及主要实现方案（`Intel® OneAPI AI Kit`）
- **数据处理和分析：** 使用 `Intel® Distribution of Modin` 中提供的加速版本 pandas 进行数据加载。使用 `Intel® Daal4py` 提供的数据处理接口进行数据的归一化等预处理操作。
- **机器学习模型：** 使用 `Intel® Extension For Scikit-Learn` 助力模型的训练与推理，调用其中实现的加速版本 sklearn 库中的 XG Boost、决策树等模型构建欺诈检测模型。使用 `Intel® Extension for PyTorch` 库提供的 pytorch 加速套件来加速神经网络的训练。
- **不平衡数据处理：** 使用 imblearn 库进行过采样、下采样和组合采样等方法处理不平衡数据集。

## 总结
在项目的实施过程中，我们深入了解了金融欺诈检测领域的挑战和解决方案。通过采用英特尔® AI 分析工具套件中的加速库和技术，我们加速了数据处理的过程，提高了模型训练和预测的效率。同时，通过对不同采样方法和模型性能的对比分析，我们学到了在处理不平衡数据集时的一些最佳实践。

**`OneAPI` 相关：**
- 利用英特尔硬件加速库提升模型性能。
- 理解和应用英特尔 AI 分析工具套件的相关组件，如`Intel® Extension for PyTorch`、`Intel® Distribution of Modin`、`Intel® Extension For Scikit-Learn`、`Intel® Daal4py`
- 在实践中我们发现，`Intel OneAPI` 的使用可以在**一整个机器学习项目**的工作周期中给用户提供很大的帮助。从加速读取数据的 modin.pandas → 加速数据预处理 daal4py 库的预处理方法 → 算法与模型层面 sklearnex  / ipex  加速，**性能提升**效果都肉眼可见
- Intel OneAPI 在机器学习上除了加速效果显著，很重要的一点是**适配性极佳，使用方便**，例如 `Intel® Distribution of Modin` 提供的加速版本 pandas 以及 `Intel® Extension For Scikit-Learn` 提供的模型算法，都无需改变原来代码的结构，只需要两行代码即可完美适配优化后的算法，带来了非常大的便利。

这个项目使我们更好地理解了金融领域的实际问题，也让我们对使用英特尔工具来优化性能有了更深入的认识。
