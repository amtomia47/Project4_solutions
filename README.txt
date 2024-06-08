F74104032 資訊114 彭昇哲

若只想看報告中的結論是否和程式一致，只需跑inference開頭的檔案
如果想重新訓練模型只需要跑main開頭的檔案

data資料夾是MNIST dataset的本體
models資料夾 是我使用的 Unet source: https://github.com/MarceloGennari/diffusion_mnist/blob/main/main.py
diffsion_model.py 是我是使用的diffusion process source: https://github.com/MarceloGennari/diffusion_mnist/blob/main/main.py

.pth &　.pt檔是模型 & DIP輸入noise的本體

requirements.txt 是我的環境中有安裝的套件
備註我有使用CUDA，請確保執行環境有安裝相關套件
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


DIP_sample.pth & DIP_sample.ipynb & input_noise.pt 是我生出來的DIP & 對應的輸入 & 生成腳本，沒事建議別動，我設計的DIP似乎具有缺陷不易收斂，跑的話可能會對實驗結果產生影響


我的solution 是 Example 1: Accelerating DDPM with DIP-based Initial Priors
Main_DIP_concat_DDPM.ipybn是本次作業的 solution 模型的訓練腳本，輸出模型為Model_DIP_DDPM.pth
inference_DIP_concat_DDPM.ipynb 是本次作業的 solution 模型的驗證腳本，讀取模型為Model_DIP_DDPM.pth

inference_DDPM_sole.ipynb & Main_DDPM_sole.ipynb 是對照組模型的 驗證&訓練腳本，讀取/輸出模型為 Model_sole_DDPM.pth

Main_schedule_modified.ipynb 是用於 part3 Ablation Studies and Analysis的模型訓練腳本
inference_modified_version2.ipynb & inference_modified_version1.ipynb 是 Part3 的 time schedule analysis 的驗證腳本，分別對應Model_DIP_DDPM_modified_schedule2.pth & Model_DIP_DDPM_modified_schedule1.pth
備註這三個檔案比較特殊，實際上inference_modified_version2.ipynb & inference_modified_version1.ipynb做的事情一樣，只是讀取的模型不同。若想驗證part3的設想重新訓練模型，只需跑Main_schedule_modified.ipynb後再跑inference_modified_version1.ipynb即可
