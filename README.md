# Voice-activity-detection-VAD-paper
Voice activity detection (VAD) paper（From 195*~2019）and its classification. The arrangement of these papers was arranged when I was studying for a double degree in UNOKI Lab of JAIST at 2019. Now share it with those in need to learn. Welcome contribution and add new related papers.

# Classification
| Method | Feature | Concept | Work Environment |
| --- | --- | --- | --- |
| G.729B VAD [6, 24] | linear spectrum frequency, zero crossing rate, full band signal energy, low band signal energy | Harmonicity | Noisy, High SNR |
| Short term feature -VAD  [1,3,51] | ZCR, energy, correlation function, Pitch detection | Short term speech features | Quiet |
| Wavelet - based VAD  [7,37,83] | Wavelet，wavelet entropy, perceptual wavelet packet decomposition | Wavelet | Noisy, High SNR |
| Entropy based VAD [20,22,30,45,82,89] | Spectral entropy, energy, spectrum | Entropy | Noisy, Stable noise |
| AMR VAD.1 [10,11,24] | pitch period, SNR, tone detection, Complex signal analysis and detection | Sub -band analysis | Noisy, high SNR |
| AMR VAD.2 [10,11,24] | channel energy, channel SNR, voice metric, frame SNR, long-term SNR | Sub-band analysis | Noisy, high SNR |
| Cepstrum based [2,4,18] | MFCC, PLCC | Cepstrum | Noisy / stationary noise |
| Spectral Peaks-based [52,57] | Spectral Peaks feature | Spectral Peaks | Noisy |
| Speech enhancement (spectral subtraction) based VAD [56] | Energy | Speech enhancement two steps processing | Noisy |
| MTF - VAD  [71,86] | Temporal power envelope | MTF | Reverberant / stationary noise |
| EMD - based VAD  [66,80] | empirical mode decomposition and modulation spectrum analysis | EMD | Noisy/Stationary noise |
| LSTV/LSFM -VAD [58,69, 79, 85] | degree of non-stationarity, Auto-correlation, spectral flatness, spectral variation | Long term variation | Noisy, unstationary noise |
| Kalman filter-based [48] | log-Mel spectral | Kalman filter | Noisy |
| HMM/Bayesian/GMM/clustering/spectral clustering(unsupervised) -based VAD [12, 13, 21, 36,37,38,47,61,68, 75,81] | MFCC, correlation function, energy, spectra-gram, wavelet, Mel-subband | Statistics (Unsupervised, supervised) | Noisy, stationary, unstationary |
| LDA -based VAD [33] | Frequency Filtering features | LDA | Reverberant |
| SVM - based VAD  [27,44,67,89] | MFCC, Entropy, spectral distortion, full-band energy difference, low-band energy difference, the zero-crossing difference | SVM | Noisy |
| DNN/CNN/LSTM based VAD [72,82,92,94,95,97, 102, 76,77,84,88,91,96] | Pitch, MFCC, LPC, PLP phase, and spectra-gram. | Deep learning | Noisy / unstable noise |

# References

[1]Freeman, D.K.; Southcott, C.B.; Boyd, I.; Cosier, G. A voice activity detector for pan-European digital cellular mobile telephone service. In Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing, Glasgow, Scotland, 23–26 May 1989; pp. 369–372

[2]J-C Junqua, Hisashi Wakita, "A comparative study of cepstral lifters and distance measures for all pole models of speech in noise", Proc. ICASSP, pp. 476-479, 1989. （cepstral coefficient）

[3]R Tucker, "Voice activity detection using a periodicity measure", IEE Proceedings I (Communications Speech and Vision), vol. 139, no. 4, pp. 377-380, 1992. （pitch detection）

[4]Haigh, J.A.; Mason, J.S. Robust voice activity detection using cepstral features. In Proceedings of the IEEE Region 10 Conference on Computer, Communication, Control and Power Engineering, Beijing, China,19–21 October 1993; pp. 321–324.

[5]Haigh, J.A. & Mason, John. (1993). Robust voice activity detection using cepstral features. IEEE TEN-CON. 321 - 324 vol.3. 10.1109/TENCON.1993.327987. 

[6]ITU, Coding of Speech and 8 kbit/s Using Conjugate Structure Algebraic Code -Excited Linear Prediction. Annex B: A Silence Compression Scheme for G.729 Optimized for Terminals Conforming to Recommend. V.70, International Telecommunication Union, 1996.

[7]Stegmann J, Schroder G. Robust voice-activity detection based on the wavelet transform[C]// IEEE Workshop on Speech Coding for Telecommunications Proceeding. IEEE, 1997.

[8]Itoh, K.; Mizushima, M. Environmental noise reduction based on speech/non-speech identiﬁcation for hearing aids. In Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing, Munich, Germany, 21–24 April 1997; pp. 419–422.

[9]R. Sarikaya and J. H. L. Hansen, “Robust speech activity detection in the presence of noise,” in Proc. 5th Int. Conf. Spoken Language Processing,1997, pp. 922–925.

[10]Adaptive Multi Rate (AMR) Speech; ANSI-C code for AMR Speech Codec, 1998.

[11]Digital Cellular Telecommunications System (Phase 2+); Adaptive Multi Rate (AMR); Speech Processing Functions; General Description,1998

[12]J. Sohn and W. Sung, “A voice activity detector employing soft decision based noise spectrum adaptation,” Proc. IEEE Int. Conf. Acoust., Speech, Signal Process., pp. 365–368, 1998 

[13]J. Sohn and W. Sung, “A voice activity detector employing soft deci-sion based noise spectrum adaptation,” in Proc. IEEE ICASSP’98, vol.1, Seattle, WA, 1998, pp. 365–368.

[14]Sohn J , Kim N S , Sung W . A statistical model-based voice activity detection[J]. IEEE Signal Processing Letters, 1999, 6(1):1-3.

[15]Malah D . System and method for noise threshold adaptation for voice activity detection in nonstationary noise environments[J]. Journal of the Acoustical Society of America, 2000, 108(3):885.

[16]Press E . Method and device for voice activity detection and a communication device[J]. Journal of the Acoustical Society of America, 2000, 108(1):21.

[17]Mekuria F . Non-parametric voice activity detection: US 2000.

[18]Nemer, E.; Goubron, R.; Mahmoud, S. Robust voice activity detection using higher-order statistics in the LPC residual domain. IEEE Trans. Speech Audio Process. 2001,9, 217–231. 

[19]E. Nemer, R. Goubran, S. Mahmoud, "Robust voice activity detection using higher-order statistics in the LPC residual domain", IEEE Trans. Speech Audio Process., vol. 9, no. 3, pp. 217-231, 2001.

[20]F. Beritelli, S. Casale, and G. Ruggeri, “Performance evaluation and comparison of ITU-T/ETSI voice activity detectors,” in Proc. IEEE ICASSP’01, vol. 3, Salt Lake City, UT, 2001, pp. 1425–1428.

[21]Y. D. Cho, K. Al-Naimi, and A. Kondoz, “Improved statistical voice activity detection based on a smoothed statistical likelihood ratio,” in Proc. IEEE ICASSP’01, vol. 2, Salt Lake City, UT, 2001, pp. 737–740

[22]Nemer E . Robust voice activity detection using higher-order statistics in the LPC residual domain[J]. IEEE Transactions On Speech And Audio Processing, 2001, 9(3):217-231.

[23]P. Renevey and A. Drygajlo, “Entropy based voice activity detection in very noisy conditions,” Proc. Eurospeech, pp. 1887–1890, Sep. 2001.

[24]Beritelli, F.; Casale, S.; Ruggeri, G.; Serano, S. Performance Evaluation and Comparison of G.729/AMR/Fuzzy Voice Activity Detectors. IEEE Signal Process. Let. 2002,9, 85–88

[25]Tanyer S G , Ozer H . Voice activity detection in nonstationary noise[J]. IEEE Transactions on Speech and Audio Processing, 2002, 8(4):478-482.

[26]Sangwan, A.; Chiranth, M.C.; Jamadagni, H.S.; Sah, R.; Venkatesha Prasad, R.; Gaurav, V. VAD techniques for real-time speech transmission on the Internet. In Proceedings of the 5th IEEE International Conference on High Speed Networks and Multimedia 
Communications, Jeju Island, Korea, 3–5 July 2002; pp. 46–50

[27]Dong E, Liu G, Zhou Y, et al. Applying Support Vector Machines to Voice Activity Detection[J]. 2003.

[28]Tian Y , Wu J , Wang Z , et al. Fuzzy clustering and Bayesian information criterion based threshold estimation for robust voice activity detection.[C]// IEEE International Conference on Acoustics. IEEE, 2003.

[29]Joon-Hyuk Chang, Nam Soo Kim, "Voice activity detection based on complex laplacian model", Electron. Lett., vol. 39, no. 7, pp. 632-634, 2003

[30]Ramirez, J.; Segura, J.C.; Benitez, C.; Torre, A.; Rubio, A. Efﬁcient voice activity algorithms using long-term speech information. Speech Commun. 2004,42, 271–287.

[31]Li Y, Zhang R, Cui H, et al. Voice activity detection algorithm with low signal-to-noise ratios based on the spectrum entropy[J]. Journal of Tsinghua University, 2005.

[32]5. J. Ramírez, J. C. Segura, C. Benítez, L. García, A. Rubio, "Statistical voice activity detection using a multiple observation likelihood ratio test", IEEE Signal Process. Lett., vol. 12, no. 10, pp. 689-692, 2005. 

[33]Jaume Padrell, Dusan Macho, Climent Nadeu, "Robust speech activity detection using lda applied to ff parameters", Proc. ICASSP, vol. 1, pp. I-557, 2005. 

[34]Zhang, L.; Gao, Y.-C.; Bian, Z.-Z.; Chen, L. Voice activity detection algorithm improvement in multi-rate speech coding of 3GPP. In Proceedings of the 2005 International Conference on Wireless Communications,Networking and Mobile Computing, (WCNM 2005), 
Wuhan, China, 23–26 September 2005; pp. 1257–1260.

[35]Kristjansson, T.; Deligne, S.; Olsen, P.A. Voicing features for robust speech detection. In Proceedings of the Ninth European Conference on Speech Communication and Technology, Lisbon, Portugal, 4–8 September 2005; pp. 369–372.

[36]Davis, A.; Nordholm, S.; Togneri, R. Statistical Voice Activity Detection Using Low-Variance Spectrum Estimation and an Adaptive Threshold. IEEE Trans. Audio Speech Lang. Process. 2006,14, 412–424. 

[37]Lee, Y.-C.; Ahn, S.-S. Statistical Model-Based VAD algorithm with wavelet transform. IEICE Trans. Fundam. Electron. Commun. Comput. Sci. 2006,E89-A, 1594–1600

[38]J. H. Chang, N. S. Kim, and S. K. Mitra, “Voice activity detection based on multiple statistical models,” IEEE Trans. Signal Process., vol. 54, no. 6, pp. 1965–1976, Jun. 2006.

[39]Li X , Liu H , Zheng Y , et al. Robust Speech Endpoint Detection Based on Improved Adaptive Band-Partitioning Spectral Entropy[M]// Bio-Inspired Computational Intelligence and Applications. Springer Berlin Heidelberg, 2007.

[40] J. Ramírez, J. Segura, J. Górriz, and L. García, “Improved voice activity detection using contextual multiple hypothesis testing for robust speech recognition,” IEEE Trans. Audio, Speech, Lang. Process., vol. 15, no. 8, pp. 2177–2189, Nov. 2007.

[41]R. Tahmasbi and S. Rezaei, “A soft voice activity detection using GARCH filter and variance Gamma distribution,” IEEE Trans. Audio, Speech, Lang. Process., vol. 15, no. 4, pp. 1129–1134, May 2007.

[42]Sakai H , Cincarek T , Kawanami H , et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model[C]// International Icst Conference on Robot Communication & Coordination. 2007.

[43]Sakai H , Cincarek T , Kawanami H , et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model[C]// International Icst Conference on Robot Communication & Coordination. 2007.

[44]T. Kinnunen, E. Chermenko, M. Tuononen, P. Franti and H. Li, Voice activity detection using mfcc features and support vector machine, Proc. Speech and Computer 2 (2007), 556–561. 

[45]D.G. Ha, S.J. Cho, G.G. Jin and O.K, Shin, Voice activity detection based on signal energy and entropy-difference in noisy environments, Journal of the Korean Society of Marine Engineering 32 (2008), 768–774.

[46]M. Asgari, A. Sayadian, M. Farhadloo and E.A. Mehrizi, Voice activity detection using entropy in spectrum domain, Proc. Telecommunication Networks and Applications Conference, 2008, 407–410.

[47]S. I. Kang, Q. H. Jo, and J. H. Chang, “Discriminative weight training for a statistical model-based voice activity detection,” IEEE Signal Process. Lett., vol. 15, pp. 170–173, 2008.

[48]M. Fujimoto and K. Ishizuka, “Noise robust voice activity detection based on switching Kalman filter,” IEICE Trans. Inf. Syst., vol. 91, no. 3, pp. 467–477, 2008.

[49]R. J. Weiss and T. T. Kristjansson, “DySANA: Dynamic speech and noise adaptation for voice activity detection,” in Proc. Interspeech, 2008, pp. 127–130.

[50]Huang H , Lin F . A speech feature extraction method using complexity measure for voice activity detection in WGN[J]. Speech Communication, 2009, 51(9):714-723.

[51]Moattar M H, Homayounpour M M . A simple but efficient real-time Voice Activity Detection algorithm[C]// European Signal Processing Conference. IEEE, 2009.

[52]Yoo I C , Yook D . Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds[J]. ETRI Journal, 2009, 31(4):451-453.

[53]Yoo I C , Yook D . Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds[J]. ETRI Journal, 2009, 31(4):451-453.

[54]Asgari M , Sayadian A , Tehranipour F , et al. Novel Voice Activity Detection Based on Vector Quantization[C]// International Conference on Computer Modelling & Simulation. IEEE, 2009.

[55]G.K. Choi and S.H. Kim, Voice activity detection method using psycho-acoustic model based on speech energy maxi-mization in noisy environments, Journal of the Acoustical Society of Korea 28 (2009), 447–453. 

[56]Hsieh, C.-H.; Feng, T.-Y.; Huang, P.-C. Energy-based VAD with grey magnitude spectral subtraction. Speech Commun. 2009,51, 810–819. 

[57]I.-C. Yoo and D. Yook, “Robust voice activity detection using the spectral peaks of vowel sounds,” ETRI J., vol. 31, pp. 451–453, Aug. 2009.

[58]Ghosh P K , Tsiartas A , Narayanan S . Robust Voice Activity Detection Using Long-Term Signal Variability[J]. IEEE Transactions on Audio, Speech, and Language Processing, 2010, 19(3):600-613.

[59]Fukuda T , Ichikawa O , Nishimura M . Long-Term Spectro-Temporal and Static Harmonic Features for Voice Activity Detection[J]. IEEE Journal of Selected Topics in Signal Processing, 2010, 4(5):834-844.

[60]L. N. Tan, B. J. Borgstrom, and A. Alwan, “Voice activity detection using harmonic frequency components in likelihood ratio test,” in Proc. IEEE Int. Conf. Acoust., Speech, Signal Process., Mar. 2010, pp. 4466–4469.

[61]J. W. Shin, J. H. Chang, and N. S. Kim, “Voice activity detection based on statistical models and machine learning approaches,” Comput. Speech Lang., vol. 24, no. 3, pp. 515–530, 2010.

[62]N.Dhananjaya and B.Yegnanarayana, “Voiced/nonvoiced detection based on robustness of voiced epochs,” IEEE Signal Process. Lett., vol. 17, no. 3, pp. 273–276, Mar. 2010.

[63]Ishizuka, K.; Nakatani, T.; Fujimoto, M.; Miyazaki, N. Noise robust voice activity detection based on periodic to aperiodic component ratio. Speech Commun. 2010,52, 41–60. 

[64]H. Ghaemmaghami, B. J. Baker, R. J. Vogt, and S. Sridharan, “Noise robust voice activity detection using features extracted from the time domain auto-correlation function,” in Proc. Interspeech, Makuhari, Japan, 2010, pp. 3118–3121.

[65]K. Ishizuka, T. Nakatani, M. Fujimoto, and N. Miyazaki, “Noise robust voice activity detection based on periodic to aperiodic component ratio,” Speech Commun., vol. 52, no. 1, pp. 41–60, Jan. 2010.

[66]Liu B S, Lu Z M, Shen L R , et al. Voice activity detection with low signal-to-noise ratio based on Hilbert-Huang transform[J]. Journal of Jilin University (Engineering and Technology Edition), 2011, 41(3):844-848.

[67]Ji Wu, Xiao-Lei Zhang, "Efficient multiple kernel support vector machine-based voice activity detection", IEEE Signal Process. Lett., vol. 18, no. 8, pp. 466-499, 2011.

[68]D. Ying, Y. Yan, J. Dang, and F. Soong, “Voice activity detection based on an unsupervised learning framework,” IEEE Trans. Audio, Speech, Lang. Process., vol. 19, no. 8, pp. 2624–2644, Nov. 2011.

[69]Ghosh, P.K.; Tsiartas, A.; Narayanan, S. Robust Voice Activity Detection Using Long-Term Signal Variability. IEEE Trans. Audio Speech Lang. Process. 2011,19, 600–613. 

[70]Moattar M H , Homayounpour M M . A Weighted Feature Voting Approach for Robust and Real-Time Voice Activity Detection[J]. Etri Journal, 2011, 33(1):99–109.

[71]Unoki,M.,Lu,X.,Petrick,R.,Morita,S.,Akagi,M.,&Hoffmann, R. (2011). Voice activity detection in MTF-based power envelope restoration. In Proceedings Interspeech2011 (pp. 2609–2612). 

[72]Zhang X L, Wu J. Deep Belief Networks Based Voice Activity Detection[J]. IEEE Transactions on Audio Speech and Language Processing, 2013, 21(4):697-710.

[73]Peng Teng, Yunde Jia, "Voice activity detection via noise reducing using non-negative sparse coding", IEEE Signal Process. Lett., vol. 20, no. 5, pp. 475-478, 2013.

[74]Shi-Wen Deng, Ji-Qing Han, "Statistical voice activity detection based on sparse representation over learned dictionary", Digital Signal Process., vol. 23, no. 4, pp. 1228-1232, 2013.

[75]Mousazadeh S , Cohen I . Voice Activity Detection in Presence of Transient Noise Using Spectral Clustering[J]. IEEE Transactions on Audio Speech and Language Processing, 2013, 21(6):1261-1271.

[76]T. Hughes and K. Mierle, “Recurrent neural networks for voice activity detection,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2013, pp. 7378–7382.

[77]F. Eyben, F. Weninger, S. Squartini, and B. Schuller, “Real-life voice activity detectionwith LSTM recurrent neural networks and an application to Hollywoodmovies,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2013, pp. 483–487.

[78]Ma, Y.; Nishihara, A. Efﬁcient voice activity detection algorithm using long-term spectral ﬂatness measure. EURASIP J. Audio Speech Music Process. 2013,2013. 

[79]Yanna Ma, Akinori Nishihara. Efficient voice activity detection algorithm using long-term spectral flatness measure[J]. 2013, 2013(1):87.

[80]Kanai Y , Unoki M . Robust voice activity detection using empirical mode decomposition and modulation spectrum analysis[C]// International Symposium on Chinese Spoken Language Processing. IEEE, 2013.

[81]S. O. Sadjadi and J. H. Hansen, “Unsupervised speech activity detection using voicing measures and perceptual spectral flux,” IEEE Signal Process. Lett., vol. 20, no. 3, pp. 197–200, Mar. 2013.

[82]N. Ryant, M. Liberman, and J. Yuan, “Speech activity detection on YouTube using deep neural networks,” in Proc. Interspeech, 2013, pp. 728–731.

[83]Gihyoun L , Sung Dae N , Jin-Ho C , et al. Voice activity detection algorithm using perceptual wavelet entropy neighbor slope[J]. Bio-medical materials and engineering, 2014, 24(6):3295-301.

[84]S. Thomas, S. Ganapathy, G. Saon, and H. Soltau, “Analyzing convolutional neural networks for speech activity detection in mismatched acoustic conditions,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2014, pp. 2519–2523.

[85]Shi, W.; Zou, Y.; Liu, Y. Long-term auto-correlation statistics based on voice activity detection for strong noisy speech. In Proceedings of the 2014 IEEE China Summit & International Conference on Signal and Information Processing, Xi’an, China, 9–13 July 
2014; pp. 100–104.

[86]Morita, Shota & Unoki, Masashi & lu, Xugang & Akagi, Masato. (2015). Robust Voice Activity Detection Based on Concept of Modulation Transfer Function in Noisy Reverberant Environments. Journal of Signal Processing Systems. 82. 10.1007/s11265-015-1014-4. 

[87]Zhang Y , Wang K , Yan B . Speech endpoint detection algorithm with low signal-to-noise based on improved conventional spectral entropy[C]// Intelligent Control & Automation. IEEE, 2016.

[88]S. Meier and W. Kellermann, “Artificial neural network-based feature combination for spatial voice activity detection,” in Proc. Interspeech, 2016, pp. 2987–2991.

[89]Johny E R , Vasuki P , Mohanalin J . Voice Activity Detection Using Fuzzy Entropy and Support Vector Machine[J]. Entropy, 2016, 18(8):298-.

[90]R. Zazo, T. N. Sainath, G. Simko, and C. Parada, “Feature learning with raw-waveform CLDNNs for voice activity detection,” in Proc. Interspeech, 2016, pp. 8–12.

[91]J. Kim, J. Kim, S. Lee, J. Park, and M. Hahn, “Vowel based voice activity detection with LSTM recurrent neural network,” in Proc. 8th Int. Conf. Signal Process. Syst., 2016, pp. 134–137.

[92]F. Vesperini, P. Vecchiotti, E. Principi, S. Squartini, and F. Piazza, “Deep neural networks for multi-room voice activity detection: Advancements and comparative evaluation,” in Proc. Int. Joint Conf. Neural Netw., 2016, pp. 3391–3398.

[93]T. Drugman,Y. Stylianou,Y. Kida, and M. Akamine, “Voice activity detection: Merging source and filter-based information,” IEEE Signal Process. Lett., vol. 23, no. 2, pp. 252–256, Feb. 2016.

[94]X.-L. Zhang and D.-L. Wang, “Boosting contextual information for deep neural network based voice activity detection,” IEEE/ACM Trans. Audio, Speech, Lang. Process., vol. 24, no. 2, pp. 252–264, Feb. 2016.

[95]Inyoung Hwang, Hyung-Min Park, Joon-Hyuk Chang, "Ensemble of deep neural networks using acoustic environment classification for statistical model-based voice activity detection", Computer Speech & Lang., vol. 38, pp. 1-12, 2016.

[96]D. A. Silva, J. A. Stuchi, R. P. V. Violato, and L. G. D. Cuozzo, “Exploring convolutional neural networks for voice activity detection,” in Cognitive Technologies. Cham, Switzerland: Springer, 2017, pp. 37–47.

[97]Longbiao Wang, Khomdet Phapatanaburi, Zeyan Go, Seiichi Nakagawa, Masahiro Iwahashi, Jianwu Dang, "Phase aware deep neural network for noise robust voice activity detection", Proc. ICME, pp. 1087-1092, 2017.

[98]Kim J , Hahn M . Voice Activity Detection Using an Adaptive Context Attention Model[J]. IEEE Signal Processing Letters, 2018:1-1.

[99]Jong Hwan Ko, Josh Fromm, Matthai Philipose, Ivan Tashev, Shuayb Zarar, "Limiting numerical precision of neural networks to achieve real-time voice activity detection", Proc. ICASSP, pp. 2236-2240, 2018.

[100]Wissam A. Jassim, Naomi Harte, "Voice activity detection using neurograms", Proc. ICASSP, pp. 5524-5528, 2018.

[101]Youngmoon Jung, Younggwan Kim, Yeunju Choi, Hoirin Kim, "Joint learning using denoising variational autoencoders for voice activity detection", Proc. Interspeech, pp. 1210-1214, 2018.

[102]Z. Fan, Z. Bai, X. Zhang, S. Rahardja and J. Chen, "AUC Optimization for Deep Learning Based Voice Activity Detection," ICASSP 2019 - 2019 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), Brighton, United Kingdom, 2019, pp. 
6760-6764.

[103]Freeman, D.K.; Southcott, C.B.; Boyd, I.; Cosier, G. A voice activity detector for pan-European digital cellular mobile telephone service. In Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing, Glasgow, Scotland, 23–26 May 1989; pp. 369–372

[104]J-C Junqua, Hisashi Wakita, "A comparative study of cepstral lifters and distance measures for all pole models of speech in noise", Proc. ICASSP, pp. 476-479, 1989. （cepstral coefficient）

[105]R Tucker, "Voice activity detection using a periodicity measure", IEE Proceedings I (Communications Speech and Vision), vol. 139, no. 4, pp. 377-380, 1992. （pitch detection）

[106]Haigh, J.A.; Mason, J.S. Robust voice activity detection using cepstral features. In Proceedings of the IEEE Region 10 Conference on Computer, Communication, Control and Power Engineering, Beijing, China,19–21 October 1993; pp. 321–324.

[107]Haigh, J.A. & Mason, John. (1993). Robust voice activity detection using cepstral features. IEEE TEN-CON. 321 - 324 vol.3. 10.1109/TENCON.1993.327987. 

[108]ITU, Coding of Speech and 8 kbit/s Using Conjugate Structure Algebraic Code -Excited Linear Prediction. Annex B: A Silence Compression Scheme for G.729 Optimized for Terminals Conforming to Recommend. V.70, International Telecommunication Union, 1996.

[109]Stegmann J , Schroder G . Robust voice-activity detection based on the wavelet transform[C]// IEEE Workshop on Speech Coding for Telecommunications Proceeding. IEEE, 1997.

[110]Itoh, K.; Mizushima, M. Environmental noise reduction based on speech/non-speech identiﬁcation for hearing aids. In Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing, Munich, Germany, 21–24 April 1997; pp. 419–422.

[111]R. Sarikaya and J. H. L. Hansen, “Robust speech activity detection in the presence of noise,” in Proc. 5th Int. Conf. Spoken Language Processing,1997, pp. 922–925.

[112]Adaptive Multi Rate (AMR) Speech; ANSI-C code for AMR Speech Codec, 1998.

[113]Digital Cellular Telecommunications System (Phase 2+); Adaptive Multi Rate (AMR); Speech Processing Functions; General Description,1998

[114]J. Sohn and W. Sung, “A voice activity detector employing soft decision based noise spectrum adaptation,” in Proc. IEEE ICASSP’98, vol.1, Seattle, WA, 1998, pp. 365–368.

[115]Sohn J , Kim N S , Sung W . A statistical model-based voice activity detection[J]. IEEE Signal Processing Letters, 1999, 6(1):1-3.

[116]Malah D . System and method for noise threshold adaptation for voice activity detection in non-stationary noise environments[J]. Journal of the Acoustical Society of America, 2000, 108(3):885.

[117]Press E . Method and device for voice activity detection and a communication device[J]. Journal of the Acoustical Society of America, 2000, 108(1):21.

[118]Mekuria F . Non-parametric voice activity detection: US 2000.

[119]Nemer, E.; Goubron, R.; Mahmoud, S. Robust voice activity detection using higher-order statistics in the LPC residual domain. IEEE Trans. Speech Audio Process. 2001,9, 217–231. 

[120]F. Beritelli, S. Casale, and G. Ruggeri, “Performance evaluation and comparison of ITU-T/ETSI voice activity detectors,” in Proc. IEEE ICASSP’01, vol. 3, Salt Lake City, UT, 2001, pp. 1425–1428.

[121]Y. D. Cho, K. Al-Naimi, and A. Kondoz, “Improved statistical voice activity detection based on a smoothed statistical likelihood ratio,” in Proc. IEEE ICASSP’01, vol. 2, Salt Lake City, UT, 2001, pp. 737–740

[122]P. Renevey and A. Drygajlo, “Entropy based voice activity detection in very noisy conditions,” Proc. Eurospeech, pp. 1887–1890, Sep. 2001.

[123]Beritelli, F.; Casale, S.; Ruggeri, G.; Serano, S. Performance Evaluation and Comparison of G.729/AMR/Fuzzy Voice Activity Detectors. IEEE Signal Process. Let. 2002,9, 85–88

[124]Tanyer S G , Ozer H . Voice activity detection in nonstationary noise[J]. IEEE Transactions on Speech and Audio Processing, 2002, 8(4):478-482.

[125]Sangwan, A.; Chiranth, M.C.; Jamadagni, H.S.; Sah, R.; Venkatesha Prasad, R.; Gaurav, V. VAD techniques for real-time speech transmission on the Internet. In Proceedings of the 5th IEEE International Conference on High Speed Networks and Multimedia 
Communications, Jeju Island, Korea, 3–5 July 2002; pp. 46–50

[126]Dong E, Liu G, Zhou Y, et al. Applying Support Vector Machines to Voice Activity Detection[J]. 2003.

[127]Tian Y , Wu J , Wang Z , et al. Fuzzy clustering and Bayesian information criterion based threshold estimation for robust voice activity detection.[C]// IEEE International Conference on Acoustics. IEEE, 2003.

[128]Joon-Hyuk Chang, Nam Soo Kim, "Voice activity detection based on complex laplacian model", Electron. Lett., vol. 39, no. 7, pp. 632-634, 2003

[129]Ramirez, J.; Segura, J.C.; Benitez, C.; Torre, A.; Rubio, A. Efﬁcient voice activity algorithms using long-term speech information. Speech Commun. 2004,42, 271–287.

[130]Li Y, Zhang R, Cui H, et al. Voice activity detection algorithm with low signal-to-noise ratios based on the spectrum entropy[J]. Journal of Tsinghua University, 2005.

[131]5. J. Ramírez, J. C. Segura, C. Benítez, L. García, A. Rubio, "Statistical voice activity detection using a multiple observation likelihood ratio test", IEEE Signal Process. Lett., vol. 12, no. 10, pp. 689-692, 2005. 

[132]Jaume Padrell, Dusan Macho, Climent Nadeu, "Robust speech activity detection using lda applied to ff parameters", Proc. ICASSP, vol. 1, pp. I-557, 2005. 

[133]Zhang, L.; Gao, Y.-C.; Bian, Z.-Z.; Chen, L. Voice activity detection algorithm improvement in multi-rate speech coding of 3GPP. In Proceedings of the 2005 International Conference on Wireless Communications,Networking and Mobile Computing, (WCNM 2005), 
Wuhan, China, 23–26 September 2005; pp. 1257–1260.

[134]Kristjansson, T.; Deligne, S.; Olsen, P.A. Voicing features for robust speech detection. In Proceedings of the Ninth European Conference on Speech Communication and Technology, Lisbon, Portugal, 4–8 September 2005; pp. 369–372.

[135]Davis, A.; Nordholm, S.; Togneri, R. Statistical Voice Activity Detection Using Low-Variance Spectrum Estimation and an Adaptive Threshold. IEEE Trans. Audio Speech Lang. Process. 2006,14, 412–424. 

[136]Lee, Y.-C.; Ahn, S.-S. Statistical Model-Based VAD algorithm with wavelet transform. IEICE Trans. Fundam. Electron. Commun. Comput. Sci. 2006,E89-A, 1594–1600

[137]J. H. Chang, N. S. Kim, and S. K. Mitra, “Voice activity detection based on multiple statistical models,” IEEE Trans. Signal Process., vol. 54, no. 6, pp. 1965–1976, Jun. 2006.

[138]Li X , Liu H , Zheng Y , et al. Robust Speech Endpoint Detection Based on Improved Adaptive Band-Partitioning Spectral Entropy[M]// Bio-Inspired Computational Intelligence and Applications. Springer Berlin Heidelberg, 2007.

[139] J. Ramírez, J. Segura, J. Górriz, and L. García, “Improved voice activity detection using contextual multiple hypothesis testing for robust speech recognition,” IEEE Trans. Audio, Speech, Lang. Process., vol. 15, no. 8, pp. 2177–2189, Nov. 2007.

[140]R. Tahmasbi and S. Rezaei, “A soft voice activity detection using GARCH filter and variance Gamma distribution,” IEEE Trans. Audio, Speech, Lang. Process., vol. 15, no. 4, pp. 1129–1134, May 2007.

[141]Sakai H , Cincarek T , Kawanami H , et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model[C]// International Icst Conference on Robot Communication & Coordination. 2007.

[142]Sakai H , Cincarek T , Kawanami H , et al. Voice Activity Detection Applied to Hands-Free Spoken Dialogue Robot based on Decoding using Acoustic and Language Model[C]// International Icst Conference on Robot Communication & Coordination. 2007.

[143]T. Kinnunen, E. Chermenko, M. Tuononen, P. Franti and H. Li, Voice activity detection using mfcc features and support vector machine, Proc. Speech and Computer 2 (2007), 556–561. 

[144]D.G. Ha, S.J. Cho, G.G. Jin and O.K, Shin, Voice activity detection based on signal energy and entropy-difference in noisy environments, Journal of the Korean Society of Marine Engineering 32 (2008), 768–774.

[145]M. Asgari, A. Sayadian, M. Farhadloo and E.A. Mehrizi, Voice activity detection using entropy in spectrum domain, Proc. Telecommunication Networks and Applications Conference, 2008, 407–410.

[146]S. I. Kang, Q. H. Jo, and J. H. Chang, “Discriminative weight training for a statistical model-based voice activity detection,” IEEE Signal Process. Lett., vol. 15, pp. 170–173, 2008.

[147]M. Fujimoto and K. Ishizuka, “Noise robust voice activity detection based on switching Kalman filter,” IEICE Trans. Inf. Syst., vol. 91, no. 3, pp. 467–477, 2008.

[148]R. J. Weiss and T. T. Kristjansson, “DySANA: Dynamic speech and noise adaptation for voice activity detection,” in Proc. Interspeech, 2008, pp. 127–130.

[149]Huang H , Lin F . A speech feature extraction method using complexity measure for voice activity detection in WGN[J]. Speech Communication, 2009, 51(9):714-723.

[150]Moattar M H , Homayounpour M M . A simple but efficient real-time Voice Activity Detection algorithm[C]// European Signal Processing Conference. IEEE, 2009.

[151]Yoo I C , Yook D . Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds[J]. ETRI Journal, 2009, 31(4):451-453.

[152]Yoo I C , Yook D . Robust Voice Activity Detection Using the Spectral Peaks of Vowel Sounds[J]. ETRI Journal, 2009, 31(4):451-453.

[153]Asgari M , Sayadian A , Tehranipour F , et al. Novel Voice Activity Detection Based on Vector Quantization[C]// International Conference on Computer Modelling & Simulation. IEEE, 2009.

[154]G.K. Choi and S.H. Kim, Voice activity detection method using psycho-acoustic model based on speech energy maxi-mization in noisy environments, Journal of the Acoustical Society of Korea 28 (2009), 447–453. 

[155]Hsieh, C.-H.; Feng, T.-Y.; Huang, P.-C. Energy-based VAD with grey magnitude spectral subtraction. Speech Commun. 2009,51, 810–819. 

[156]I.-C. Yoo and D. Yook, “Robust voice activity detection using the spectral peaks of vowel sounds,” ETRI J., vol. 31, pp. 451–453, Aug. 2009.

[157]Ghosh P K , Tsiartas A , Narayanan S . Robust Voice Activity Detection Using Long-Term Signal Variability[J]. IEEE Transactions on Audio, Speech, and Language Processing, 2010, 19(3):600-613.

[158]Fukuda T , Ichikawa O , Nishimura M . Long-Term Spectro-Temporal and Static Harmonic Features for Voice Activity Detection[J]. IEEE Journal of Selected Topics in Signal Processing, 2010, 4(5):834-844.

[159]L. N. Tan, B. J. Borgstrom, and A. Alwan, “Voice activity detection using harmonic frequency components in likelihood ratio test,” in Proc. IEEE Int. Conf. Acoust., Speech, Signal Process., Mar. 2010, pp. 4466–4469.

[160]J. W. Shin, J. H. Chang, and N. S. Kim, “Voice activity detection based on statistical models and machine learning approaches,” Comput. Speech Lang., vol. 24, no. 3, pp. 515–530, 2010.

[161]N.Dhananjaya and B.Yegnanarayana, “Voiced/nonvoiced detection based on robustness of voiced epochs,” IEEE Signal Process. Lett., vol. 17, no. 3, pp. 273–276, Mar. 2010.

[162]Ishizuka, K.; Nakatani, T.; Fujimoto, M.; Miyazaki, N. Noise robust voice activity detection based on periodic to aperiodic component ratio. Speech Commun. 2010,52, 41–60. 

[163]H. Ghaemmaghami, B. J. Baker, R. J. Vogt, and S. Sridharan, “Noise robust voice activity detection using features extracted from the timedomain autocorrelation function,” in Proc. Interspeech, Makuhari, Japan, 2010, pp. 3118–3121.

[164]K. Ishizuka, T. Nakatani, M. Fujimoto, and N. Miyazaki, “Noise robust voice activity detection based on periodic to aperiodic component ratio,” Speech Commun., vol. 52, no. 1, pp. 41–60, Jan. 2010.

[165]Liu B S , Lu Z M , Shen L R , et al. Voice activity detection with low signal-to-noise ratio based on Hilbert-Huang transform[J]. Journal of Jilin University(Engineering and Technology Edition), 2011, 41(3):844-848.

[166]Ji Wu, Xiao-Lei Zhang, "Efficient multiple kernel support vector machine based voice activity detection", IEEE Signal Process. Lett., vol. 18, no. 8, pp. 466-499, 2011.

[167]D. Ying, Y. Yan, J. Dang, and F. Soong, “Voice activity detection based on an unsupervised learning framework,” IEEE Trans. Audio, Speech, Lang. Process., vol. 19, no. 8, pp. 2624–2644, Nov. 2011.

[168]Moattar M H , Homayounpour M M . A Weighted Feature Voting Approach for Robust and Real-Time Voice Activity Detection[J]. Etri Journal, 2011, 33(1):99–109.

[169]Unoki,M.,Lu,X.,Petrick,R.,Morita,S.,Akagi,M.,&Hoffmann, R. (2011). Voice activity detection in MTF-based power envelope restoration. In Proceedings Interspeech2011 (pp. 2609–2612). 

[170]Zhang X L , Wu J . Deep Belief Networks Based Voice Activity Detection[J]. IEEE Transactions on Audio Speech and Language Processing, 2013, 21(4):697-710.

[171]Peng Teng, Yunde Jia, "Voice activity detection via noise reducing using non-negative sparse coding", IEEE Signal Process. Lett., vol. 20, no. 5, pp. 475-478, 2013.

[172]Shi-Wen Deng, Ji-Qing Han, "Statistical voice activity detection based on sparse representation over learned dictionary", Digital Signal Process., vol. 23, no. 4, pp. 1228-1232, 2013.

[173]Mousazadeh S , Cohen I . Voice Activity Detection in Presence of Transient Noise Using Spectral Clustering[J]. IEEE Transactions on Audio Speech and Language Processing, 2013, 21(6):1261-1271.

[174]T. Hughes and K. Mierle, “Recurrent neural networks for voice activity detection,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2013, pp. 7378–7382.

[175]F. Eyben, F. Weninger, S. Squartini, and B. Schuller, “Real-life voice activity detectionwith LSTM recurrent neural networks and an application to Hollywoodmovies,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2013, pp. 483–487.

[176]Ma, Y.; Nishihara, A. Efﬁcient voice activity detection algorithm using long-term spectral ﬂatness measure. EURASIP J. Audio Speech Music Process. 2013,2013. 

[177]Kanai Y , Unoki M . Robust voice activity detection using empirical mode decomposition and modulation spectrum analysis[C]// International Symposium on Chinese Spoken Language Processing. IEEE, 2013.

[178]S. O. Sadjadi and J. H. Hansen, “Unsupervised speech activity detection using voicing measures and perceptual spectral flux,” IEEE Signal Process. Lett., vol. 20, no. 3, pp. 197–200, Mar. 2013.

[179]N. Ryant, M. Liberman, and J. Yuan, “Speech activity detection on YouTube using deep neural networks,” in Proc. Interspeech, 2013, pp. 728–731.

[180]Gihyoun L , Sung Dae N , Jin-Ho C , et al. Voice activity detection algorithm using perceptual wavelet entropy neighbor slope[J]. Bio-medical materials and engineering, 2014, 24(6):3295-301.

[181]S. Thomas, S. Ganapathy, G. Saon, and H. Soltau, “Analyzing convolutional neural networks for speech activity detection in mismatched acoustic conditions,” in Proc. Int. Conf. Acoust., Speech, Signal Process., 2014, pp. 2519–2523.

[182]Shi, W.; Zou, Y.; Liu, Y. Long-term auto-correlation statistics based on voice activity detection for strong noisy speech. In Proceedings of the 2014 IEEE China Summit & International Conference on Signal and Information Processing, Xi’an, China, 9–13 July 
2014; pp. 100–104.

[183]Morita, Shota & Unoki, Masashi & lu, Xugang & Akagi, Masato. (2015). Robust Voice Activity Detection Based on Concept of Modulation Transfer Function in Noisy Reverberant Environments. Journal of Signal Processing Systems. 82. 10.1007/s11265-015-1014-4. 

[184]Zhang Y , Wang K , Yan B . Speech endpoint detection algorithm with low signal-to-noise based on improved conventional spectral entropy[C]// Intelligent Control & Automation. IEEE, 2016.

[185]S. Meier and W. Kellermann, “Artificial neural network-based feature combination for spatial voice activity detection,” in Proc. Interspeech, 2016, pp. 2987–2991.

[186]Johny E R , Vasuki P , Mohanalin J . Voice Activity Detection Using Fuzzy Entropy and Support Vector Machine[J]. Entropy, 2016, 18(8):298-.

[187]R. Zazo, T. N. Sainath, G. Simko, and C. Parada, “Feature learning with raw-waveform CLDNNs for voice activity detection,” in Proc. Interspeech, 2016, pp. 8–12.

[188]J. Kim, J. Kim, S. Lee, J. Park, and M. Hahn, “Vowel based voice activity detection with LSTM recurrent neural network,” in Proc. 8th Int. Conf. Signal Process. Syst., 2016, pp. 134–137.

[189]F. Vesperini, P. Vecchiotti, E. Principi, S. Squartini, and F. Piazza, “Deep neural networks for multi-room voice activity detection: Advancements and comparative evaluation,” in Proc. Int. Joint Conf. Neural Netw., 2016, pp. 3391–3398.

[190]T. Drugman,Y. Stylianou,Y. Kida, and M. Akamine, “Voice activity detection: Merging source and filter-based information,” IEEE Signal Process. Lett., vol. 23, no. 2, pp. 252–256, Feb. 2016.

[191]X.-L. Zhang and D.-L. Wang, “Boosting contextual information for deep neural network based voice activity detection,” IEEE/ACM Trans. Audio, Speech, Lang. Process., vol. 24, no. 2, pp. 252–264, Feb. 2016.

[192]Inyoung Hwang, Hyung-Min Park, Joon-Hyuk Chang, "Ensemble of deep neural networks using acoustic environment classification for statistical model-based voice activity detection", Computer Speech & Lang., vol. 38, pp. 1-12, 2016.

[193]D. A. Silva, J. A. Stuchi, R. P. V. Violato, and L. G. D. Cuozzo, “Exploring convolutional neural networks for voice activity detection,” in Cognitive Technologies. Cham, Switzerland: Springer, 2017, pp. 37–47.

[194]Longbiao Wang, Khomdet Phapatanaburi, Zeyan Go, Seiichi Nakagawa, Masahiro Iwahashi, Jianwu Dang, "Phase aware deep neural network for noise robust voice activity detection", Proc. ICME, pp. 1087-1092, 2017.

[195]Kim J , Hahn M . Voice Activity Detection Using an Adaptive Context Attention Model[J]. IEEE Signal Processing Letters, 2018:1-1.

[196]Jong Hwan Ko, Josh Fromm, Matthai Philipose, Ivan Tashev, Shuayb Zarar, "Limiting numerical precision of neural networks to achieve real-time voice activity detection", Proc. ICASSP, pp. 2236-2240, 2018.

[197]Wissam A. Jassim, Naomi Harte, "Voice activity detection using neurograms", Proc. ICASSP, pp. 5524-5528, 2018.

[198]Youngmoon Jung, Younggwan Kim, Yeunju Choi, Hoirin Kim, "Joint learning using denoising variational autoencoders for voice activity detection", Proc. Interspeech, pp. 1210-1214, 2018.

[199]Z. Fan, Z. Bai, X. Zhang, S. Rahardja and J. Chen, "AUC Optimization for Deep Learning Based Voice Activity Detection," ICASSP 2019 - 2019 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), Brighton, United Kingdom, 2019, pp. 
6760-6764.

