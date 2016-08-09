# songci-rnn
Generating Songci (Poetry of the Song Dynasty) by machine. Based on QuanSongci and RNN.   
[Live Demo](http://seeleit.com/songci)  
If the sample result is shit, you can refresh the page to make it surprise you.
***
## How to use
1. Get [torch-rnn](https://github.com/jcjohnson/torch-rnn). **torch-rnn** is based on [Torch7](http://torch.ch/), you should set up Torch environment first. 
2. Copy the **songci.txt** to ``torch-rnn/data/``
3. Enter ``torch-rnn`` directory
4. You can train your own model or use my provided model. Run   
    ```
    python scripts/preprocess.py --input_txt data/songci.txt --output_h5 songci.h5 --output_json songci.json
    
    # train the model
    th train.lua -input_h5 songci.h5 -input_json songci.json -gpu -1  # without gpu
    
    # sample text
    th sample.lua -checkpoint cv/checkpoint_yourcheckpoint.t7 -length 200 -gpu -1
    
    # or you can sample text from my trained model
     th sample.lua -checkpoint songci_epoch50_loss5.106.t7 -length 200 -gpu -1
    ```
***
 
# 吟·宋词
通过全宋词训练RNN，随机生成宋词   
[在线版](http://seeleit.com/songci)  
如果生成结果很烂，你可尝试多刷新几次，总会惊艳到你。有些反正我是不相信这竟然是机器生成的（= =）。
***
## 使用
1. 下载 [torch-rnn](https://github.com/jcjohnson/torch-rnn). **torch-rnn** 基于 [Torch7](http://torch.ch/), 你应该先配置Torch环境. 
2. 拷贝 **songci.txt** 到 ``torch-rnn/data/``
3. 进入 ``torch-rnn`` 目录
4. 你可以自己训练模型也可以用我提供的模型.   
    ```
    python scripts/preprocess.py --input_txt data/songci.txt --output_h5 songci.h5 --output_json songci.json
    
    # 训练
    th train.lua -input_h5 songci.h5 -input_json songci.json -gpu -1  # cpu模式
    
    # 生成文本
    th sample.lua -checkpoint cv/checkpoint_yourcheckpoint.t7 -length 200 -gpu -1
    
    # 用我提供的模型生成文本
     th sample.lua -checkpoint songci_epoch50_loss5.106.t7 -length 200 -gpu -1
    ```
 

> If you have any problem, please contact hevlhayt@foxmail.com (ﾉﾟ▽ﾟ)ﾉ


   
