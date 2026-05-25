# 语音活动检测 (VAD) — 论文与代码

[![中文](https://img.shields.io/badge/中文-README-red)](README_CN.md) [![English](https://img.shields.io/badge/English-README-blue)](README.md)

[![Stars](https://img.shields.io/github/stars/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Forks](https://img.shields.io/github/forks/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Watchers](https://img.shields.io/github/watchers/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Last Commit](https://img.shields.io/github/last-commit/linan2/Voice-activity-detection-VAD-paper-and-code)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)

---

## 简介

**语音活动检测 (Voice Activity Detection, VAD)** 是一种基于声学特征的统计分布来判断音频信号片段中是否包含语音的技术。它在各类语音应用的前端处理中起着关键作用，包括：

- 语音增强 (Speech Enhancement)
- 鲁棒语音识别系统 (Robust Speech Recognition Systems)
- 说话人识别 (Speaker Recognition)

本仓库汇集了 VAD 相关的研究论文（涵盖 **1980 年代至 2024 年**）及其对应的开源代码实现，按方法类别进行整理，旨在为从事 VAD 研究的科研人员和工程师提供全面的参考资料。

> **正在进行的工作**：我目前正在开发一个脚本，利用开源噪声数据集和纯净语音数据集来合成音频，用于深度学习模型的训练和推理。该脚本也将很快开源。如果你有更好的脚本，欢迎贡献！

---

## 目录

- [代码实现](#代码实现)
- [方法分类](#方法分类)
- [数据集](#数据集)
- [参考文献](#参考文献)
- [如何贡献](#如何贡献)
- [引用格式](#引用格式)

---

## 代码实现

### 推荐 / 热门项目
| 项目 | 链接 | 简介 |
|------|------|------|
| **VAD_MATLAB** | [github.com/linan2/VAD_MATLAB](https://github.com/linan2/VAD_MATLAB) | 多种 VAD 算法的 MATLAB 实现 |
| **rVAD** | [github.com/zhenghuatan/rVAD](https://github.com/zhenghuatan/rVAD) | 高效的 VAD 算法，推荐优先使用（优于 Sohn VAD） |
| **FireRedVAD** | [github.com/FireRedTeam/FireRedASR2S](https://github.com/FireRedTeam/FireRedASR2S) | 支持 100+ 种语言（语音/歌唱/音乐检测）。**F1 = 97.57%**，性能优于 Silero-VAD、TEN-VAD 和 FunASR-VAD。支持流式和非流式 VAD |
| **Silero-VAD** | [github.com/snakers4/silero-vad](https://github.com/snakers4/silero-vad) | 流行的预训练 VAD 模型，广泛应用于生产环境 |
| **TEN VAD** | [github.com/TEN-framework/ten-vad](https://github.com/TEN-framework/ten-vad) | 企业级实时 VAD。精度高于 WebRTC/Silero VAD，计算和内存开销更低，有效降低对话式 AI 的端到端延迟 |
| **FSMN-VAD (阿里巴巴)** | [modelscope.cn/models/damo/...](https://www.modelscope.cn/models/damo/speech_fsmn_vad_zh-cn-16k-common-pytorch/summary) | 阿里巴巴 ModelScope 基于 FSMB 架构的 VAD 模型 |
| **FSMN-VAD (开源实现)** | [github.com/lovemefan/fsmn-vad](https://github.com/lovemefan/fsmn-vad) | 基于 FSMN 的 VAD 开源实现 |
| **SpeechBrain VAD** | [github.com/speechbrain/.../VAD](https://github.com/speechbrain/speechbrain/tree/develop/recipes/LibriParty/VAD) | SpeechBrain 深度学习工具包中的 VAD 方案 |

### 传统 / 经典方法
| 项目 | 链接 | 简介 |
|------|------|------|
| **Sohn VAD** | [github.com/eesungkim/Voice_Activity_Detector](https://github.com/eesungkim/Voice_Activity_Detector) | 经典的基于统计模型的 VAD（实践中 rVAD 性能更优） |
| **WebRTC VAD** | [github.com/wiseman/py-webrtcvad](https://github.com/wiseman/py-webrtcvad) | Google WebRTC VAD 引擎的 Python 封装 |
| **MRCG-VAD** | [github.com/jtkim-kaist/VAD](https://github.com/jtkim-kaist/VAD) | 基于 MRCG 特征的 VAD（代码较旧但特征设计有参考价值） |
| **LTPD-VAD** | [github.com/Cruze-Young/LTPD-VAD](https://github.com/Cruze-Young/LTPD-VAD) | 基于长时基音依赖的 VAD（作者未测试） |

---

## 方法分类

| 方法 | 特征 | 核心思想 | 适用环境 |
|------|------|----------|----------|
| **G.729B VAD** [6, 24] | 线性频谱频率、过零率、全带/低带能量 | 谐波性 | 噪声环境，高信噪比 |
| **短时特征 VAD** [1, 3, 51] | 过零率、能量、相关性、基音检测 | 短时语音特征 | 安静环境 |
| **基于小波的 VAD** [7, 37, 83] | 小波、小波熵、感知小波包分解 | 小波变换 | 噪声环境，高信噪比 |
| **基于熵的 VAD** [20, 22, 30, 45, 82, 89] | 谱熵、能量、频谱 | 熵 | 噪声环境，平稳噪声 |
| **AMR VAD.1** [10, 11, 24] | 基音周期、信噪比、音调检测 | 子带分析 | 噪声环境，高信噪比 |
| **AMR VAD.2** [10, 11, 24] | 信道能量、信道信噪比、语音度量 | 子带分析 | 噪声环境，高信噪比 |
| **基于倒谱的 VAD** [2, 4, 18] | MFCC、PLCC | 倒谱 | 噪声/平稳噪声环境 |
| **谱峰 VAD** [52, 57] | 谱峰特征 | 谱峰 | 噪声环境 |
| **语音增强 VAD** [56] | 能量 | 谱减法（两步法） | 噪声环境 |
| **MTF-VAD** [71, 86] | 时域功率包络 | 调制传递函数 | 混响/平稳噪声环境 |
| **基于 EMD 的 VAD** [66, 80] | EMD、调制谱分析 | 经验模态分解 | 噪声/平稳噪声环境 |
| **LSTV/LSFM-VAD** [58, 69, 79, 85] | 非平稳性、自相关、谱平坦度 | 长时变化 | 噪声环境，非平稳噪声 |
| **卡尔曼滤波 VAD** [48] | Log-Mel 频谱 | 卡尔曼滤波 | 噪声环境 |
| **HMM/贝叶斯/GMM/聚类 VAD** [12, 13, 21, 36, 37, 38, 47, 61, 68, 75, 81] | MFCC、相关性、能量、频谱图、小波 | 统计方法（有监督/无监督） | 噪声环境，平稳/非平稳噪声 |
| **LDA 基 VAD** [33] | 频率滤波特征 | 线性判别分析 | 混响环境 |
| **基于 SVM 的 VAD** [27, 44, 67, 89] | MFCC、熵、谱失真、能量差 | 支持向量机 | 噪声环境 |
| **DNN/CNN/LSTM VAD** [72, 82, 92, 94, 95, 97, 102, 200, 201] | 基音、MFCC、LPC、PLP 相位、频谱图、掩码听觉/调制编码器 | 深度学习 | 噪声/非平稳噪声环境 |

---

## 数据集

### 噪声数据集
| 数据集 | 链接 | 简介 |
|--------|------|------|
| **MUSAN** | [openslr.org/17](http://www.openslr.org/17/) | 音乐、语音和噪声语料库（142 小时） |
| **Noisex92** | - | 经典的噪声评估数据集 |
| **Non-Speech-100** | - | 100 段非语音音频片段 |
| **RIR_Noise** | [openslr.org/28](http://www.openslr.org/28/) | 房间脉冲响应和噪声数据集。[添加混响的代码](https://github.com/linan2/add_reverb2) |
| **DEMOND** | - | 环境噪声数据集 |
| **DNS Challenge** | [github.com/microsoft/DNS-Challenge](https://github.com/microsoft/DNS-Challenge) | 微软深度噪声抑制挑战赛数据集 |

### 语音数据集
| 数据集 | 链接 | 简介 |
|--------|------|------|
| **WSJ** | - | 华尔街日报语料库 |
| **TIMIT** | - | 音素平衡的朗读语音语料库 |
| **TED-LIUM** | [openslr.org/7](http://www.openslr.org/7/) | TED 演讲语音语料库 |
| **LibriSpeech** | [openslr.org/12](http://www.openslr.org/12/) | 1000 小时英文朗读语音语料库 |
| **AISHELL** | [openslr.org/33](http://www.openslr.org/33/) | 178 小时普通话语音语料库 |

---

## 参考文献

### 1980 年代 - 2000 年代：早期传统方法

[1] Freeman, D.K.; Southcott, C.B.; Boyd, I.; Cosier, G. A voice activity detector for pan-European digital cellular mobile telephone service. In *Proc. IEEE ICASSP*, Glasgow, Scotland, 23-26 May 1989; pp. 369-372.

[2] Junqua, J-C.; Wakita, H. A comparative study of cepstral lifters and distance measures for all pole models of speech in noise. In *Proc. ICASSP*, 1989, pp. 476-479.

[3] Tucker, R. Voice activity detection using a periodicity measure. *IEE Proc. I (Communications, Speech and Vision)*, 1992, 139(4), pp. 377-380.

[4] Haigh, J.A.; Mason, J.S. Robust voice activity detection using cepstral features. In *Proc. IEEE TENCON*, Beijing, China, 19-21 October 1993; pp. 321-324.

[6] ITU-T. Coding of speech at 8 kbit/s using CS-ACELP - Annex B: A silence compression scheme for G.729. *ITU-T Recommendation G.729*, 1996.

[7] Stegmann, J.; Schroder, G. Robust voice-activity detection based on the wavelet transform. In *IEEE Workshop on Speech Coding*, 1997.

[8] Itoh, K.; Mizushima, M. Environmental noise reduction based on speech/non-speech identification for hearing aids. In *Proc. IEEE ICASSP*, Munich, Germany, 21-24 April 1997; pp. 419-422.

[9] Sarikaya, R.; Hansen, J.H. Robust speech activity detection in the presence of noise. In *Proc. 5th Int. Conf. Spoken Language Processing*, 1997, pp. 922-925.

[10] ETSI. Adaptive Multi Rate (AMR) Speech; ANSI-C code for AMR Speech Codec, 1998.

[11] ETSI. Digital Cellular Telecommunications System (Phase 2+); Adaptive Multi Rate (AMR); Speech Processing Functions; General Description, 1998.

[12] Sohn, J.; Sung, W. A voice activity detector employing soft decision based noise spectrum adaptation. In *Proc. IEEE ICASSP*, vol. 1, Seattle, WA, 1998, pp. 365-368.

[13] Sohn, J.; Sung, W. A voice activity detector employing soft decision based noise spectrum adaptation. In *Proc. IEEE ICASSP'98*, vol. 1, Seattle, WA, 1998, pp. 365-368.

[14] Sohn, J.; Kim, N.S.; Sung, W. A statistical model-based voice activity detection. *IEEE Signal Processing Letters*, 1999, 6(1), pp. 1-3.

[15] Malah, D. System and method for noise threshold adaptation for voice activity detection in non-stationary noise environments. *Journal of the Acoustical Society of America*, 2000, 108(3), 885.

[16] Press, E. Method and device for voice activity detection and a communication device. *Journal of the Acoustical Society of America*, 2000, 108(1), 21.

[17] Mekuria, F. Non-parametric voice activity detection. US Patent, 2000.

[18] Nemer, E.; Goubran, R.; Mahmoud, S. Robust voice activity detection using higher-order statistics in the LPC residual domain. *IEEE Trans. Speech Audio Process.*, 2001, 9(3), pp. 217-231.

[19] Nemer, E.; Goubran, R.; Mahmoud, S. Robust voice activity detection using higher-order statistics in the LPC residual domain. *IEEE Trans. Speech Audio Process.*, 2001, 9(3), pp. 217-231.

[20] Beritelli, F.; Casale, S.; Ruggeri, G. Performance evaluation and comparison of ITU-T/ETSI voice activity detectors. In *Proc. IEEE ICASSP*, vol. 3, Salt Lake City, UT, 2001, pp. 1425-1428.

[21] Cho, Y.D.; Al-Naimi, K.; Kondoz, A. Improved statistical voice activity detection based on a smoothed statistical likelihood ratio. In *Proc. IEEE ICASSP*, vol. 2, Salt Lake City, UT, 2001, pp. 737-740.

[22] Renevey, P.; Drygajlo, A. Entropy based voice activity detection in very noisy conditions. In *Proc. Eurospeech*, 2001, pp. 1887-1890.

[23] Beritelli, F.; Casale, S.; Ruggeri, G.; Serano, S. Performance Evaluation and Comparison of G.729/AMR/Fuzzy Voice Activity Detectors. *IEEE Signal Processing Letters*, 2002, 9, pp. 85-88.

[24] Beritelli, F.; Casale, S.; Ruggeri, G.; Serano, S. Performance evaluation and comparison of G.729/AMR/Fuzzy voice activity detectors. *IEEE Signal Process. Lett.*, 2002, 9(3), pp. 85-88.

[25] Tanyer, S.G.; Ozer, H. Voice activity detection in nonstationary noise. *IEEE Transactions on Speech and Audio Processing*, 2002, 8(4), pp. 478-482.

[26] Sangwan, A. et al. VAD techniques for real-time speech transmission on the Internet. In *Proc. 5th IEEE Int. Conf. on High Speed Networks and Multimedia Communications*, Jeju Island, Korea, 3-5 July 2002; pp. 46-50.

[27] Dong, E.; Liu, G.; Zhou, Y. et al. Applying Support Vector Machines to Voice Activity Detection. 2003.

[28] Tian, Y.; Wu, J.; Wang, Z. et al. Fuzzy clustering and Bayesian information criterion based threshold estimation for robust voice activity detection. In *Proc. IEEE ICASSP*, 2003.

[29] Chang, J.H.; Kim, N.S. Voice activity detection based on complex laplacian model. *Electronics Letters*, 2003, 39(7), pp. 632-634.

[30] Ramirez, J.; Segura, J.C.; Benitez, C.; Torre, A.; Rubio, A. Efficient voice activity algorithms using long-term speech information. *Speech Communication*, 2004, 42, pp. 271-287.

[31] Li, Y.; Zhang, R.; Cui, H. et al. Voice activity detection algorithm with low signal-to-noise ratios based on the spectrum entropy. *Journal of Tsinghua University*, 2005.

[32] Ramirez, J.; Segura, J.C.; Benitez, C.; Garcia, L.; Rubio, A. Statistical voice activity detection using a multiple observation likelihood ratio test. *IEEE Signal Process. Lett.*, 2005, 12(10), pp. 689-692.

[33] Padrell, J.; Macho, D.; Nadeu, C. Robust speech activity detection using LDA applied to FF parameters. In *Proc. ICASSP*, vol. 1, 2005, pp. I-557.

[34] Zhang, L.; Gao, Y.C.; Bian, Z.Z.; Chen, L. Voice activity detection algorithm improvement in multi-rate speech coding of 3GPP. In *Proc. WCNM 2005*, Wuhan, China, 23-26 September 2005; pp. 1257-1260.

[35] Kristjansson, T.; Deligne, S.; Olsen, P.A. Voicing features for robust speech detection. In *Proc. 9th European Conf. on Speech Communication and Technology*, Lisbon, Portugal, 4-8 September 2005; pp. 369-372.

[36] Davis, A.; Nordholm, S.; Togneri, R. Statistical Voice Activity Detection Using Low-Variance Spectrum Estimation and an Adaptive Threshold. *IEEE Trans. Audio Speech Lang. Process.*, 2006, 14(2), pp. 412-424.

[37] Lee, Y.C.; Ahn, S.S. Statistical Model-Based VAD algorithm with wavelet transform. *IEICE Trans. Fundam. Electron. Commun. Comput. Sci.*, 2006, E89-A(6), pp. 1594-1600.

[38] Chang, J.H.; Kim, N.S.; Mitra, S.K. Voice activity detection based on multiple statistical models. *IEEE Trans. Signal Process.*, 2006, 54(6), pp. 1965-1976.

[39] Li, X.; Liu, H.; Zheng, Y. et al. Robust Speech Endpoint Detection Based on Improved Adaptive Band-Partitioning Spectral Entropy. In *Bio-Inspired Computational Intelligence and Applications*, Springer, 2007.

[40] Ramirez, J.; Segura, J.C.; Gorriz, J.; Garcia, L. Improved voice activity detection using contextual multiple hypothesis testing for robust speech recognition. *IEEE Trans. Audio, Speech, Lang. Process.*, 2007, 15(8), pp. 2177-2189.

[41] Tahmasbi, R.; Rezaei, S. A soft voice activity detection using GARCH filter and variance Gamma distribution. *IEEE Trans. Audio, Speech, Lang. Process.*, 2007, 15(4), pp. 1129-1134.

[42] Sakai, H. et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model. In *Proc. ICST Conf. on Robot Communication & Coordination*, 2007.

[43] Sakai, H. et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model. In *Proc. ICST Conf. on Robot Communication & Coordination*, 2007.

[44] Kinnunen, T. et al. Voice activity detection using MFCC features and support vector machine. In *Proc. SPECOM*, 2007, pp. 556-561.

[45] Ha, D.G.; Cho, S.J.; Jin, G.G.; Shin, O.K. Voice activity detection based on signal energy and entropy-difference in noisy environments. *Journal of the Korean Society of Marine Engineering*, 2008, 32, pp. 768-774.

[46] Asgari, M. et al. Voice activity detection using entropy in spectrum domain. In *Proc. Telecommunication Networks and Applications Conference*, 2008, pp. 407-410.

[47] Kang, S.I.; Jo, Q.H.; Chang, J.H. Discriminative weight training for a statistical model-based voice activity detection. *IEEE Signal Process. Lett.*, 2008, 15, pp. 170-173.

[48] Fujimoto, M.; Ishizuka, K. Noise robust voice activity detection based on switching Kalman filter. *IEICE Trans. Inf. Syst.*, 2008, 91(3), pp. 467-477.

[49] Weiss, R.J.; Kristjansson, T.T. DySANA: Dynamic speech and noise adaptation for voice activity detection. In *Proc. Interspeech*, 2008, pp. 127-130.

[50] Huang, H.; Lin, F. A speech feature extraction method using complexity measure for voice activity detection in WGN. *Speech Communication*, 2009, 51(9), pp. 714-723.

[51] Moattar, M.H.; Homayounpour, M.M. A simple but efficient real-time Voice Activity Detection algorithm. In *Proc. European Signal Processing Conference (EUSIPCO)*, 2009.

[52] Yoo, I.C.; Yook, D. Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds. *ETRI Journal*, 2009, 31(4), pp. 451-453.

[53] Yoo, I.C.; Yook, D. Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds. *ETRI Journal*, 2009, 31(4), pp. 451-453.

[54] Asgari, M. et al. Novel Voice Activity Detection Based on Vector Quantization. In *Proc. International Conference on Computer Modelling & Simulation*, 2009.

[55] Choi, G.K.; Kim, S.H. Voice activity detection method using psycho-acoustic model based on speech energy maximization in noisy environments. *Journal of the Acoustical Society of Korea*, 2009, 28, pp. 447-453.

[56] Hsieh, C.H.; Feng, T.Y.; Huang, P.C. Energy-based VAD with grey magnitude spectral subtraction. *Speech Communication*, 2009, 51(8), pp. 810-819.

[57] Yoo, I.C.; Yook, D. Robust voice activity detection using the spectral peaks of vowel sounds. *ETRI Journal*, 2009, 31(4), pp. 451-453.

### 2010 年代：统计模型与深度学习

[58] Ghosh, P.K.; Tsiartas, A.; Narayanan, S. Robust Voice Activity Detection Using Long-Term Signal Variability. *IEEE Transactions on Audio, Speech, and Language Processing*, 2010, 19(3), pp. 600-613.

[59] Fukuda, T.; Ichikawa, O.; Nishimura, M. Long-Term Spectro-Temporal and Static Harmonic Features for Voice Activity Detection. *IEEE Journal of Selected Topics in Signal Processing*, 2010, 4(5), pp. 834-844.

[60] Tan, L.N.; Borgstrom, B.J.; Alwan, A. Voice activity detection using harmonic frequency components in likelihood ratio test. In *Proc. IEEE ICASSP*, 2010, pp. 4466-4469.

[61] Shin, J.W.; Chang, J.H.; Kim, N.S. Voice activity detection based on statistical models and machine learning approaches. *Computer Speech & Language*, 2010, 24(3), pp. 515-530.

[62] Dhananjaya, N.; Yegnanarayana, B. Voiced/nonvoiced detection based on robustness of voiced epochs. *IEEE Signal Process. Lett.*, 2010, 17(3), pp. 273-276.

[63] Ishizuka, K.; Nakatani, T.; Fujimoto, M.; Miyazaki, N. Noise robust voice activity detection based on periodic to aperiodic component ratio. *Speech Communication*, 2010, 52(1), pp. 41-60.

[64] Ghaemmaghami, H. et al. Noise robust voice activity detection using features extracted from the time domain auto-correlation function. In *Proc. Interspeech*, 2010, pp. 3118-3121.

[65] Ishizuka, K. et al. Noise robust voice activity detection based on periodic to aperiodic component ratio. *Speech Communication*, 2010, 52(1), pp. 41-60.

[66] Liu, B.S. et al. Voice activity detection with low signal-to-noise ratio based on Hilbert-Huang transform. *Journal of Jilin University (Engineering and Technology Edition)*, 2011, 41(3), pp. 844-848.

[67] Wu, J.; Zhang, X.L. Efficient multiple kernel support vector machine-based voice activity detection. *IEEE Signal Process. Lett.*, 2011, 18(8), pp. 466-499.

[68] Ying, D. et al. Voice activity detection based on an unsupervised learning framework. *IEEE Trans. Audio, Speech, Lang. Process.*, 2011, 19(8), pp. 2624-2644.

[69] Ghosh, P.K.; Tsiartas, A.; Narayanan, S. Robust Voice Activity Detection Using Long-Term Signal Variability. *IEEE Trans. Audio Speech Lang. Process.*, 2011, 19(3), pp. 600-613.

[70] Moattar, M.H.; Homayounpour, M.M. A Weighted Feature Voting Approach for Robust and Real-Time Voice Activity Detection. *ETRI Journal*, 2011, 33(1), pp. 99-109.

[71] Unoki, M. et al. Voice activity detection in MTF-based power envelope restoration. In *Proc. Interspeech*, 2011, pp. 2609-2612.

[72] Zhang, X.L.; Wu, J. Deep Belief Networks Based Voice Activity Detection. *IEEE Transactions on Audio Speech and Language Processing*, 2013, 21(4), pp. 697-710.

[73] Teng, P.; Jia, Y. Voice activity detection via noise reducing using non-negative sparse coding. *IEEE Signal Process. Lett.*, 2013, 20(5), pp. 475-478.

[74] Deng, S.W.; Han, J.Q. Statistical voice activity detection based on sparse representation over learned dictionary. *Digital Signal Process.*, 2013, 23(4), pp. 1228-1232.

[75] Mousazadeh, S.; Cohen, I. Voice Activity Detection in Presence of Transient Noise Using Spectral Clustering. *IEEE Transactions on Audio Speech and Language Processing*, 2013, 21(6), pp. 1261-1271.

[76] Hughes, T.; Mierle, K. Recurrent neural networks for voice activity detection. In *Proc. IEEE ICASSP*, 2013, pp. 7378-7382.

[77] Eyben, F. et al. Real-life voice activity detection with LSTM recurrent neural networks and an application to Hollywood movies. In *Proc. IEEE ICASSP*, 2013, pp. 483-487.

[78] Ma, Y.; Nishihara, A. Efficient voice activity detection algorithm using long-term spectral flatness measure. *EURASIP J. Audio Speech Music Process.*, 2013.

[79] Ma, Y.; Nishihara, A. Efficient voice activity detection algorithm using long-term spectral flatness measure. *EURASIP Journal on Audio, Speech, and Music Processing*, 2013.

[80] Kanai, Y.; Unoki, M. Robust voice activity detection using empirical mode decomposition and modulation spectrum analysis. In *Proc. ISCSLP*, 2013.

[81] Sadjadi, S.O.; Hansen, J.H. Unsupervised speech activity detection using voicing measures and perceptual spectral flux. *IEEE Signal Process. Lett.*, 2013, 20(3), pp. 197-200.

[82] Ryant, N.; Liberman, M.; Yuan, J. Speech activity detection on YouTube using deep neural networks. In *Proc. Interspeech*, 2013, pp. 728-731.

[83] Lee, G. et al. Voice activity detection algorithm using perceptual wavelet entropy neighbor slope. *Bio-medical Materials and Engineering*, 2014, 24(6), pp. 3295-3301.

[84] Thomas, S. et al. Analyzing convolutional neural networks for speech activity detection in mismatched acoustic conditions. In *Proc. IEEE ICASSP*, 2014, pp. 2519-2523.

[85] Shi, W.; Zou, Y.; Liu, Y. Long-term auto-correlation statistics based voice activity detection for strong noisy speech. In *Proc. IEEE ChinaSIP*, Xi'an, China, 2014, pp. 100-104.

[86] Morita, S.; Unoki, M. et al. Robust Voice Activity Detection Based on Concept of Modulation Transfer Function in Noisy Reverberant Environments. *Journal of Signal Processing Systems*, 2015.

[87] Zhang, Y.; Wang, K.; Yan, B. Speech endpoint detection algorithm with low signal-to-noise based on improved conventional spectral entropy. In *Proc. ICICA*, 2016.

[88] Meier, S.; Kellermann, W. Artificial neural network-based feature combination for spatial voice activity detection. In *Proc. Interspeech*, 2016, pp. 2987-2991.

[89] Johny, E.R.; Vasuki, P.; Mohanalin, J. Voice Activity Detection Using Fuzzy Entropy and Support Vector Machine. *Entropy*, 2016, 18(8), 298.

[90] Zazo, R. et al. Feature learning with raw-waveform CLDNNs for voice activity detection. In *Proc. Interspeech*, 2016, pp. 8-12.

[91] Kim, J. et al. Vowel based voice activity detection with LSTM recurrent neural network. In *Proc. 8th Int. Conf. Signal Process. Syst.*, 2016, pp. 134-137.

[92] Vesperini, F. et al. Deep neural networks for multi-room voice activity detection: Advancements and comparative evaluation. In *Proc. Int. Joint Conf. Neural Netw.*, 2016, pp. 3391-3398.

[93] Drugman, T. et al. Voice activity detection: Merging source and filter-based information. *IEEE Signal Process. Lett.*, 2016, 23(2), pp. 252-256.

[94] Zhang, X.L.; Wang, D.L. Boosting contextual information for deep neural network based voice activity detection. *IEEE/ACM Trans. Audio, Speech, Lang. Process.*, 2016, 24(2), pp. 252-264.

[95] Hwang, I.; Park, H.M.; Chang, J.H. Ensemble of deep neural networks using acoustic environment classification for statistical model-based voice activity detection. *Computer Speech & Language*, 2016, 38, pp. 1-12.

[96] Silva, D.A. et al. Exploring convolutional neural networks for voice activity detection. In *Cognitive Technologies*, Springer, 2017, pp. 37-47.

[97] Wang, L. et al. Phase aware deep neural network for noise robust voice activity detection. In *Proc. ICME*, 2017, pp. 1087-1092.

### 2018 - 2024 年：现代深度学习方法

[98] Kim, J.; Hahn, M. Voice Activity Detection Using an Adaptive Context Attention Model. *IEEE Signal Processing Letters*, 2018.

[99] Ko, J.H. et al. Limiting numerical precision of neural networks to achieve real-time voice activity detection. In *Proc. IEEE ICASSP*, 2018, pp. 2236-2240.

[100] Jassim, W.A.; Harte, N. Voice activity detection using neurograms. In *Proc. IEEE ICASSP*, 2018, pp. 5524-5528.

[101] Jung, Y. et al. Joint learning using denoising variational autoencoders for voice activity detection. In *Proc. Interspeech*, 2018, pp. 1210-1214.

[102] Fan, Z. et al. AUC Optimization for Deep Learning Based Voice Activity Detection. In *Proc. IEEE ICASSP*, 2019, pp. 6760-6764.

[200] Li, N.; Wang, L.; Unoki, M. et al. Robust voice activity detection using a masked auditory encoder based convolutional neural network. In *Proc. IEEE ICASSP*, 2021.

[201] Li, N.; Wang, L.; Ge, M. et al. Robust voice activity detection using an auditory-inspired masked modulation encoder based convolutional attention network. *Speech Communication*, vol. 157, 103024, 2024.

---

## 如何贡献

欢迎贡献！如果你发现有尚未收录的 VAD 论文或开源代码，请：

1. **提交 Issue** 描述该论文/代码
2. **提交 Pull Request** 添加内容

### 贡献步骤
```bash
# Fork 本仓库
# 克隆你的 Fork
git clone https://github.com/YOUR_USERNAME/Voice-activity-detection-VAD-paper-and-code.git
# 在 References 部分添加新论文
# 如需要，更新 Classification 表格
# 提交 Pull Request
```

---

## 引用格式

如果你觉得本仓库对你有帮助，欢迎引用：

```bibtex
@misc{VAD-papers-code,
  author = {Nan Li},
  title  = {Voice Activity Detection (VAD) -- Papers and Code},
  year   = {2024},
  url    = {https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code}
}
```

如果你使用了作者本人的论文（[200], [201]），请引用：

```bibtex
@inproceedings{li2021robust,
  title     = {Robust voice activity detection using a masked auditory encoder based convolutional neural network},
  author    = {Li, Nan and Wang, Longbiao and Unoki, Masashi and others},
  booktitle = {Proc. IEEE ICASSP},
  year      = {2021},
  organization = {IEEE}
}

@article{li2024robust,
  title   = {Robust voice activity detection using an auditory-inspired masked modulation encoder based convolutional attention network},
  author  = {Li, Nan and Wang, Longbiao and Ge, Meng and others},
  journal = {Speech Communication},
  volume  = {157},
  pages   = {103024},
  year    = {2024},
  publisher = {Elsevier}
}
```

---

> **联系方式**：如有任何问题或建议，欢迎提交 Issue 或通过 GitHub 联系。
