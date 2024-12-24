# **Dynamic Optimization of Portfolio Allocation Using Deep Reinforcement Learning 论文代码**(Paper Code)

## 1. 关于（About）

论文地址（Paper URL）：http:

训练奖励（Training Rewards）：

![](.\img\training_rewards.svg)

实验结果（Experimental Results）：

![](.\img\OPT_comparison.svg)



本代码的交易环境基于[wassname](https://github.com/wassname) 的 [rl-portfolio-management](https://github.com/wassname/rl-portfolio-management) 进行改进，并将其迁移至 Stable-Baselines3 （SB3）强化学习框架。（注意：该代码仅支持Python 3.7 版本下的SB3）

This trading environment is developed based on wassname's rl-portfolio-management implementation, with improvements and migration to the Stable-Baselines3 (SB3) reinforcement learning framework. (Note: This code is compatible with SB3 under Python 3.7)



## 2. 必要的python包（Required Python Packages）

此代码只适用于在python=3.7版本下运行，请运行如下命令安装必要的python packages：
（This code is compatible with Python 3.7 only. Execute the following commands to install the required Python packages:）

pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117
pip install stable-baselines3[extra]==1.3.0
pip install notebook
pip install einops
pip install tables
pip install seaborn
pip install tqdm
pip install openpyxl

## 3. 代码运行步骤和注意事项（Code Execution Steps and Important Notes）

### （1）运行步骤（Code Execution Steps ）

配置好运行环境并安装了必要的python packages后，把此代码clone或下载到本地，直接运行ipynb文件中的代码即可。

After environment configuration and package installation, clone or download the repository locally to execute the Jupyter notebook files.

例如（For example）：

10+1assets-drl-portfolio-Longing-stableBaseline3-PPO-VGG1-softmax-maxAVGSharpe.ipynb：该文件是论文的代码文件，打开后可直接运行（This notebook implements the paper's methodology and can be executed directly.）。

12+1assets-drl-portfolio-Longing-stableBaseline3-SAC-ViT-softmax-maxAVGSharpe-patchsize3x3.ipynb：该文件对算力要求极高，仅供大家测试和学习（This notebook requires intensive computational resources and is provided for experimental and educational purposes only.）。

### （2）注意事项（Important Notes）

在./data/0. load chinese data 1d multindex.ipynb 文件中，test_split=0.08 这行代码用于划分训练集和测试集。注意：测试集的区间长度不能小于训练时随机采样的区间长度，否则会报错。例如，如果每个 episode 随机采样 128 个交易日的数据进行训练，那么测试集的区间长度就不能少于 128 天。

In ./data/0. load chinese data 1d multindex.ipynb, the parameter test_split=0.08 defines the train-test split ratio. Critical Note: To prevent runtime errors, ensure that the test period length exceeds the random sampling interval used in training. For instance, when each training episode samples 128 trading days, the test period must contain a minimum of 128 days of data.
