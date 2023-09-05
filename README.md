# 数字人主要技术整理

目前数字人主要包括形象、声音和对话能力几方面。主要交互方式为直接与数字人进行对话。

## 1. 形象

实现对话可以通过实时的方式，也可以通过先合成再播放的的方式。前者在高性能电脑中可实现非常低的延时，可用在直播中。后者有一定延时。

- 实时或非实时模型（代表技术：[Meta Human](https://www.unrealengine.com/en-US/metahuman), [NVIDIA Omniverse Audio2Face](https://www.nvidia.com/en-us/omniverse/apps/audio2face/)）
- 实时视频换脸（代表技术：[DeepFakeLive](https://www.deepfakevfx.com/downloads/deepfacelive/)）
- 非实时视频换声音（代表技术：[Wav2Lip](https://github.com/Rudrabha/Wav2Lip)）
- 非实时图片转视频（代表技术：[Sadtalker](https://github.com/OpenTalker/SadTalker)）

## 2. 声音

数字人声音可使用现有模型的TTS，或使用自训练的声音模型。声学模型是声音合成系统的重要组成部分。
![声学模型](https://i0.hdslb.com/bfs/article/439a654b5efa2b623d5e6cbd68ac525665ad737b.png@1256w_240h_!web-article-pic.avif)

主流声学模型包括[VITS](https://github.com/jaywalnut310/vits)、[Tacotron](https://github.com/NVIDIA/DeepLearningExamples/tree/master/PyTorch/SpeechSynthesis/Tacotron2)、[FastSpeech2](https://github.com/ming024/FastSpeech2)等。VITS（Variational Inference with adversarial learning for end-to-end Text-to-Speech）是一种语音合成方法，它使用预先训练好的语音编码器 (vocoder声码器) 将文本转化为语音。
![vits process](https://i0.hdslb.com/bfs/article/6fb3acf043b2842d861066653a85fff84be95af7.png@1256w_726h_!web-article-pic.avif)

之前流行的AI孙燕姿等，采用技术为[so-vits-svc](https://github.com/svc-develop-team/so-vits-svc/tree/4.1-Stable)，全称SoftVC VITS Singing Voice Conversion。该技术是一个声音爱好者基于[softVC](https://github.com/bshall/soft-vc)和[VITS](https://github.com/jaywalnut310/vits)修改而来。

- **声音转声音**（代表技术：[so-vits-svc](https://github.com/svc-develop-team/so-vits-svc/tree/4.1-Stable)，[Emotional VITS](https://github.com/innnky/emotional-vits)）
- **文字转声音**（代表技术：[阿里ModelScope](https://modelscope.cn/my/overview)，[Bark](https://github.com/suno-ai/bark)）

## 3. Large Langurage Model（LLM/大语言模型）

#### ChatGPT
官网：[https://chat.openai.com/chat](https://chat.openai.com/chat)  
openai后台：[https://platform.openai.com/](https://platform.openai.com/)  
新建API KEY：[https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)  
查看账号额度：[https://platform.openai.com/account/usage](https://platform.openai.com/account/usage)  
官方API文档：[https://platform.openai.com/docs/api-reference](https://platform.openai.com/docs/api-reference)  

#### Claude
实现参考：[claude-in-slack-api](https://github.com/yokonsan/claude-in-slack-api)  
API申请方法：[claude-api](https://github.com/bincooo/claude-api)  
slack官网：[https://slack.com/intl/zh-cn/](https://slack.com/intl/zh-cn/)  
添加claude到slack：[https://www.anthropic.com/claude-in-slack](https://www.anthropic.com/claude-in-slack)  

视频教程：  
[完美替代chatGPT！保姆级Claude注册教程及使用上的优点和缺点](https://www.bilibili.com/video/BV1PP41127mQ)  
[解决现阶段slack新建工作区Claude不回复](https://www.bilibili.com/video/BV17k4y1H7aa)  

#### Claude2
[Claude2-PyAPI](https://github.com/wwwzhouhui/Claude2-PyAPI)  
claude2官网：[https://claude.ai/](https://claude.ai/)  
cookie获取方式：F12抓包XHR，然后请求头获取cookie  

#### ChatGLM
官方仓库：[ChatGLM-6B](https://github.com/THUDM/ChatGLM-6B)  
整合包：[【ChatGLM】本地版ChatGPT？6G显存可用！ChatGLM-6B 清华开源模型一键包发布 可更新](https://www.bilibili.com/video/BV1E24y1u7Go)  

#### 智谱AI
官方：[https://open.bigmodel.cn/](https://open.bigmodel.cn/)  
api key申请地址：[https://open.bigmodel.cn/usercenter/apikeys](https://open.bigmodel.cn/usercenter/apikeys)  
注意，需要在"设置"->"账号设置"中完成实名认证后，才能使用API。新账号默认赠送了18元的免费额度。  

#### langchain-ChatGLM
官方仓库：[langchain-ChatGLM](https://github.com/chatchat-space/langchain-ChatGLM)  
个人提供的整合包：[https://pan.quark.cn/s/8d8904fd4b30](https://pan.quark.cn/s/8d8904fd4b30)  
chatglm-6b-int4模型下载(其实这个官方就行，有会员的话网盘快点)：[https://pan.quark.cn/s/a483e0c3e5fa](https://pan.quark.cn/s/a483e0c3e5fa)  
官方模型仓库：[https://huggingface.co/THUDM](https://huggingface.co/THUDM)  

## 4. 综合项目代表

- [AI-Vtuber](https://github.com/Ikaros-521/AI-Vtuber)  
【开源】AI Vtuber是一个由 【ChatterBot/ChatGPT/claude/langchain（本地/llm）/chatglm/text-generation-webui/闻达】 驱动的虚拟主播  

- [Fay](https://github.com/TheRamU/Fay)
【开源】Fay是一个完整的开源项目，包含Fay控制器及数字人模型，可灵活组合出不同的应用场景：虚拟主播、现场推销货、商品导购、语音助理、远程语音助理、数字人互动、数字人面试官及心理测评、贾维斯、Her。

- [腾讯智影](https://zenvideo.qq.com/)
【国产商用】融合多种AIGC能力的综合创作平台。

- [Motionface](https://motionface.cn/)
【国产商用】集成虚拟主播、嘴型同步、卡通风等的综合创作平台。

## 资讯

- [大模型、数字人技术在教育领域中如何得以应用？ ](https://learning.sohu.com/a/713671752_120619005)  
“用科技促进教育发展，让更多人受益，是我们的初心。构建更有效果、更有效率、更有体验感的教育，让全球的学习者都能享有优质数字教育资源。”
8月20日，在2023全球智慧教育大会现场，北京师范大学智慧学习研究院副院长、网龙副总裁陈长杰在接受媒体采访时做了上述表示。

## 项目实际体验使用说明文档（AIGC夏令营&GCD4FE 48H）

<https://yuanzhuo.bnu.edu.cn/downloads/gcd4fe_ai_story.html>
