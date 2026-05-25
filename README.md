# Voice Activity Detection (VAD) — Papers & Code

[![Stars](https://img.shields.io/github/stars/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Forks](https://img.shields.io/github/forks/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Watchers](https://img.shields.io/github/watchers/linan2/Voice-activity-detection-VAD-paper-and-code?style=social)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)
[![Last Commit](https://img.shields.io/github/last-commit/linan2/Voice-activity-detection-VAD-paper-and-code)](https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code)

---

## Introduction

**Voice Activity Detection (VAD)** is a technique that determines whether an audio signal segment contains speech or non-speech based on the statistical distribution of acoustic features. It plays a critical role in the front-end processing of various speech applications, including:

- Speech Enhancement
- Robust Speech Recognition Systems
- Speaker Recognition

This repository collects VAD-related research papers (from the **1980s to 2024**) and their corresponding open-source code implementations, organized by method category. It serves as a comprehensive reference for researchers and engineers working on VAD.

> **Work in Progress**: I am currently developing a script to synthesize audio using open-source noise datasets and clean speech datasets for deep learning training and inference. This script will also be open-sourced soon. If you have a better script, feel free to contribute!

---

## Table of Contents

- [Code Implementations](#code-implementations)
- [Method Classification](#method-classification)
- [Datasets](#datasets)
- [References](#references)
- [Contributing](#contributing)
- [Citation](#citation)

---

## Code Implementations

### Author's Own Work
| Project | Link | Description |
|---------|------|-------------|
| **VAD_MATLAB** | [github.com/linan2/VAD_MATLAB](https://github.com/linan2/VAD_MATLAB) | MATLAB implementation of various VAD algorithms (maintained by the author) |
| **rVAD** | [github.com/zhenghuatan/rVAD](https://github.com/zhenghuatan/rVAD) | An efficient VAD algorithm used in the author's papers (recommended over Sohn VAD) |

### Recommended / Popular
| Project | Link | Description |
|---------|------|-------------|
| **FireRedVAD** | [github.com/FireRedTeam/FireRedASR2S](https://github.com/FireRedTeam/FireRedASR2S) | Supports 100+ languages (speech/singing/music detection). **F1 = 97.57%**, outperforming Silero-VAD, TEN-VAD, and FunASR-VAD. Supports both streaming and non-streaming VAD |
| **Silero-VAD** | [github.com/snakers4/silero-vad](https://github.com/snakers4/silero-vad) | Popular pre-trained VAD model, widely used in production |
| **TEN VAD** | [github.com/TEN-framework/ten-vad](https://github.com/TEN-framework/ten-vad) | Enterprise-grade real-time VAD. Higher precision than WebRTC/Silero VAD with lower computational cost and memory usage. Reduces end-to-end latency in conversational AI |
| **FSMN-VAD (Alibaba)** | [modelscope.cn/models/damo/...](https://www.modelscope.cn/models/damo/speech_fsmn_vad_zh-cn-16k-common-pytorch/summary) | Alibaba ModelScope VAD model based on FSMB architecture |
| **FSMN-VAD (Open Source)** | [github.com/lovemefan/fsmn-vad](https://github.com/lovemefan/fsmn-vad) | Open-source implementation of FSMN-based VAD |
| **SpeechBrain VAD** | [github.com/speechbrain/.../VAD](https://github.com/speechbrain/speechbrain/tree/develop/recipes/LibriParty/VAD) | VAD recipe in the SpeechBrain deep learning toolkit |

### Traditional / Classic Methods
| Project | Link | Description |
|---------|------|-------------|
| **Sohn VAD** | [github.com/eesungkim/Voice_Activity_Detector](https://github.com/eesungkim/Voice_Activity_Detector) | Classic statistical model-based VAD (rVAD performs better in practice) |
| **WebRTC VAD** | [github.com/wiseman/py-webrtcvad](https://github.com/wiseman/py-webrtcvad) | Python wrapper for Google's WebRTC VAD engine |
| **MRCG-VAD** | [github.com/jtkim-kaist/VAD](https://github.com/jtkim-kaist/VAD) | VAD with MRCG features (code is outdated but features are interesting) |
| **LTPD-VAD** | [github.com/Cruze-Young/LTPD-VAD](https://github.com/Cruze-Young/LTPD-VAD) | Long-Term Pitch Dependency based VAD (not tested by the author) |

---

## Method Classification

| Method | Features | Core Concept | Suitable Environment |
|--------|---------|---------------|---------------------|
| **G.729B VAD** [6, 24] | Linear spectrum freq., ZCR, full/low band energy | Harmonicity | Noisy, High SNR |
| **Short-term Feature VAD** [1, 3, 51] | ZCR, energy, correlation, pitch detection | Short-term speech features | Quiet |
| **Wavelet-based VAD** [7, 37, 83] | Wavelet, wavelet entropy, perceptual wavelet packet decomposition | Wavelet transform | Noisy, High SNR |
| **Entropy-based VAD** [20, 22, 30, 45, 82, 89] | Spectral entropy, energy, spectrum | Entropy | Noisy, stationary noise |
| **AMR VAD.1** [10, 11, 24] | Pitch period, SNR, tone detection | Sub-band analysis | Noisy, High SNR |
| **AMR VAD.2** [10, 11, 24] | Channel energy, channel SNR, voice metric | Sub-band analysis | Noisy, High SNR |
| **Cepstrum-based VAD** [2, 4, 18] | MFCC, PLCC | Cepstrum | Noisy / stationary noise |
| **Spectral Peaks VAD** [52, 57] | Spectral peaks feature | Spectral peaks | Noisy |
| **Speech Enhancement VAD** [56] | Energy | Spectral subtraction (two-step) | Noisy |
| **MTF-VAD** [71, 86] | Temporal power envelope | Modulation Transfer Function | Reverberant / stationary noise |
| **EMD-based VAD** [66, 80] | EMD, modulation spectrum analysis | Empirical Mode Decomposition | Noisy / stationary noise |
| **LSTV/LSFM-VAD** [58, 69, 79, 85] | Non-stationarity, auto-correlation, spectral flatness | Long-term variation | Noisy, non-stationary noise |
| **Kalman Filter VAD** [48] | Log-Mel spectrum | Kalman filtering | Noisy |
| **HMM/Bayesian/GMM/Clustering VAD** [12, 13, 21, 36, 37, 38, 47, 61, 68, 75, 81] | MFCC, correlation, energy, spectrogram, wavelet | Statistical (supervised/unsupervised) | Noisy, stationary/non-stationary |
| **LDA-based VAD** [33] | Frequency filtering features | Linear Discriminant Analysis | Reverberant |
| **SVM-based VAD** [27, 44, 67, 89] | MFCC, entropy, spectral distortion, energy diff | Support Vector Machine | Noisy |
| **DNN/CNN/LSTM VAD** [72, 82, 92, 94, 95, 97, 102, 200, 201] | Pitch, MFCC, LPC, PLP phase, spectrogram | Deep Learning | Noisy / non-stationary noise |

---

## Datasets

### Noise Datasets
| Dataset | Link | Description |
|---------|------|-------------|
| **MUSAN** | [openslr.org/17](http://www.openslr.org/17/) | Music, speech, and noise corpus (142 hours) |
| **Noisex92** | - | Classic noise dataset for evaluation |
| **Non-Speech-100** | - | 100 non-speech audio clips |
| **RIR_Noise** | [openslr.org/28](http://www.openslr.org/28/) | Room impulse response and noise dataset. [Code to add reverb](https://github.com/linan2/add_reverb2) |
| **DEMOND** | - | Environmental noise dataset |
| **DNS Challenge** | [github.com/microsoft/DNS-Challenge](https://github.com/microsoft/DNS-Challenge) | Microsoft Deep Noise Suppression challenge dataset |

### Speech Datasets
| Dataset | Link | Description |
|---------|------|-------------|
| **WSJ** | - | Wall Street Journal corpus |
| **TIMIT** | - | Phonetically balanced read speech corpus |
| **TED-LIUM** | [openslr.org/7](http://www.openslr.org/7/) | TED talks speech corpus |
| **LibriSpeech** | [openslr.org/12](http://www.openslr.org/12/) | 1000-hour English read speech corpus |
| **AISHELL** | [openslr.org/33](http://www.openslr.org/33/) | 178-hour Mandarin speech corpus |

---

## References

### 1980s - 2000s: Early Traditional Methods

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

### 2010s: Statistical Models & Deep Learning

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

### 2018 - 2024: Modern Deep Learning Methods

[98] Kim, J.; Hahn, M. Voice Activity Detection Using an Adaptive Context Attention Model. *IEEE Signal Processing Letters*, 2018.

[99] Ko, J.H. et al. Limiting numerical precision of neural networks to achieve real-time voice activity detection. In *Proc. IEEE ICASSP*, 2018, pp. 2236-2240.

[100] Jassim, W.A.; Harte, N. Voice activity detection using neurograms. In *Proc. IEEE ICASSP*, 2018, pp. 5524-5528.

[101] Jung, Y. et al. Joint learning using denoising variational autoencoders for voice activity detection. In *Proc. Interspeech*, 2018, pp. 1210-1214.

[102] Fan, Z. et al. AUC Optimization for Deep Learning Based Voice Activity Detection. In *Proc. IEEE ICASSP*, 2019, pp. 6760-6764.

[200] **Li, N.**; Wang, L.; Unoki, M. et al. Robust voice activity detection using a masked auditory encoder based convolutional neural network. In *Proc. IEEE ICASSP*, 2021. :star:

[201] **Li, N.**; Wang, L.; Ge, M. et al. Robust voice activity detection using an auditory-inspired masked modulation encoder based convolutional attention network. *Speech Communication*, vol. 157, 103024, 2024. :star:

> :star: = Author's own publication

---

## Contributing

Contributions are welcome! If you know of a VAD paper or open-source code that is not yet included, please feel free to:

1. **Open an Issue** describing the paper/code
2. **Submit a Pull Request** with the addition

### How to Contribute
```bash
# Fork this repository
# Clone your fork
git clone https://github.com/YOUR_USERNAME/Voice-activity-detection-VAD-paper-and-code.git
# Add a new paper to the References section
# Update the Classification table if needed
# Submit a pull request
```

---

## Citation

If you find this repository helpful, please consider citing it:

```bibtex
@misc{VAD-papers-code,
  author = {Nan Li},
  title  = {Voice Activity Detection (VAD) -- Papers and Code},
  year   = {2024},
  url    = {https://github.com/linan2/Voice-activity-detection-VAD-paper-and-code}
}
```

If you use the author's own papers ([200], [201]), please cite:

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

> **Contact**: If you have any questions or suggestions, feel free to open an issue or reach out via GitHub.
