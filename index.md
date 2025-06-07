# <center> DeployVC: Towards Efficient and Real-time Voice Changer with Scalar Causal Convolutional Model </center>

anonymous authors


## Abstract
In this study, we propose DeployVC, an efficient and easy-to-deploy voice conversion (VC) system based on a scalar causal convolutional model for real-time communication (RTC) applications. 
Its deployability is reflected in three aspects: 
(1) It performs timbre adaptation directly on semantically-rich tokens during RTC transmission, rather than employing explicit speaker-content disentanglement.
(2) It completes VC at the token level within the encoder side, thus eliminating protocol compatibility problems on the decoder side.
(3) It attempts to model speech in a compact scalar latent space, thereby easing the high latency of cascaded VC solutions.
Specifically, we propose a novel speech codec with projection scalar quantization (PSQ-Codec), which effectively maps complex speech signals into a compact scalar latent space. 
Benefiting from PSQ-Codec, 
we design a low-complexity causal convolutional model in this scalar latent space.
To facilitate the specific timbre, we introduce a high-quality customized timbre dataset. 
We train DeployVC and previous large-scale VC models on the proposed customized dataset, which shows high-quality conversion ability and high speaker similarity. 
Comprehensive subjective and objective evaluations demonstrate improvements in both speech quality and processing latency.


# Demo of speech codecs

"Ref" denotes the reference speech. We have provided samples compressed by various codecs, including both signal processing-based and neural-based methods. In these comparisons, "PSQ-Codec@9.5kbps" specifically refers to our model.

##     Demo of female


###    English 

 |Ref |Opus@6kbps| Lyra2@6kbps | EVS@7.2kbps | Opus@8kbps | PSQ-Codec@9.5kbps| Lyra2@9.2kbps | EVS@9.6kbps | Opus@10kbps |
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
 |<audio src="demo_orig/Eng/Female/Female_01.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_02.wav" controls preload></audio> |<audio src="demo_orig/Eng/Female/Female_03.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_04.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_05.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_06.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_07.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_08.wav" controls preload></audio> | <audio src="demo_orig/Eng/Female/Female_09.wav" controls preload></audio> |
 |--- | --- | --- | --- | --- | --- | --- | --- | --- |




##     Demo of male


###    English 

 |Ref |Opus@6kbps| Lyra2@6kbps | EVS@7.2kbps | Opus@8kbps | PSQ-Codec@9.5kbps| Lyra2@9.2kbps | EVS@9.6kbps | Opus@10kbps |
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | 
 |<audio src="demo_orig/Eng/Male/Male_01.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_02.wav" controls preload></audio> |<audio src="demo_orig/Eng/Male/Male_03.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_04.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_05.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_06.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_07.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_08.wav" controls preload></audio> | <audio src="demo_orig/Eng/Male/Male_09.wav" controls preload></audio> |
 |--- | --- | --- | --- | --- | --- | --- | --- | --- | 





##     Demo of female
###    Mandarin 



|Ref | PSQ-Codec@9.5kbps | DAC@8kbps  | Encodec@12kbps   | 
|:---: | :---: | :---: | :---: |
 |<audio src="demo_orig/female/Ref_p501/p501_CN_F1_68.wav" controls preload></audio> | <audio src="demo_orig/female/DeployVC/p501_CN_F1_68.wav" controls preload></audio> |<audio src="demo_orig/female/DAC/p501_CN_F1_68.wav" controls preload></audio> | <audio src="demo_orig/female/Encodec/p501_CN_F1_68.wav" controls preload></audio> |
 |--- | --- | --- | --- |


##      Demo of male
###     Mandarin 

|Ref | PSQ-Codec@9.5kbps | DAC@8kbps  | Encodec@12kbps   | 
|:---: | :---: | :---: | :---: |
 |<audio src="demo_orig/male/Ref_p501/p501_CN_M1_70.wav" controls preload></audio> | <audio src="demo_orig/male/DeployVC/p501_CN_M1_70.wav" controls preload></audio> |<audio src="demo_orig/male/DAC/p501_CN_M1_70.wav" controls preload></audio> | <audio src="demo_orig/male/Encodec/p501_CN_M1_70.wav" controls preload></audio> |
 |--- | --- | --- | --- |






# Demo of voice changer

## Demo of target timbre 1

The “target label” denotes the actual target speech signal. 
“Ref” stands for reference timbre of target speaker.
“source” is the input speech signal. “Original” refers to our PSQ-Codec while “DeployVC” refers to our method.

**Please slide the mouse to select different files for listening**.

### English 

 |Target label |Ref | Source | Original | DeployVC | FACodec| DDDM-VC | QuickVC | DiffVC | VQMIVC|
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
 |<audio src="demo_ht/English/Target label/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/Ref/ref_eng_hutao_p239_503.wav" controls preload></audio> |<audio src="demo_ht/English/Source/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/Original/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/DeployVC/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/FACodec/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/DDDM_VC/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/QuickVC/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/DiffVC/p225_366.wav" controls preload></audio> | <audio src="demo_ht/English/VQMIVC/p225_366.wav" controls preload></audio> |
 |--- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


### Mandarin 


  
| Target label                                              |  Ref                                                         | Source                                                      | Original                                                    | DeployVC                                                | FACodec                                                    |  DDDM-VC                                                    | QuickVC                                                     | DiffVC                                                      | VQMIVC|                                                      
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
  | <audio src="demo_ht/mandarin/Target label/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/English/Ref/ref_eng_hutao_p239_503.wav" controls preload></audio> |<audio src="demo_ht/mandarin/Source/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/Original/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/DeployVC/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/FACodec/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/DDDM_VC/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/QuickVC/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/DiffVC/ht_CN_F2_14.wav" controls preload></audio> | <audio src="demo_ht/mandarin/VQMIVC/ht_CN_F2_14.wav" controls preload></audio> |
   |--- | --- | --- | --- | --- | --- | --- | --- | --- | --- |







## Demo of target timbre 2

The “target label” denotes the actual target speech signal. “Ref” stands for reference timbre of target speaker. “source” is the input speech signal. “Original” refers to our PSQ-Codec, while “DeployVC” refers to our method.

**Please slide the mouse to select different files for listening**.

### English 

 |Target label |Ref | Source | Original | DeployVC | FACodec| DDDM-VC | QuickVC | DiffVC | VQMIVC|
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
 |<audio src="demo_p231/English/Target label/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/Ref/p231_008_mic2_p231_076_mic2.wav" controls preload></audio> |<audio src="demo_p231/English/Source/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/Original/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/DeployVC/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/FACodec/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/DDDM_VC/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/QuickVC/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/DiffVC/p236_503.wav" controls preload></audio> | <audio src="demo_p231/English/VQMIVC/p236_503.wav" controls preload></audio> |
 |--- | --- | --- | --- | --- | --- | --- | --- | --- | --- |



### Mandarin 

| Target label                                              |  Ref                                                         | Source                                                      | Original                                                    | DeployVC                                                | FACodec                                                     | DDDM-VC                                                     | QuickVC                                                     | DiffVC                                                      | VQMIVC|                                                      
 |:--- |:--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
  | <audio src="demo_p231/mandarin/Target label/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/Ref/p231_008_mic2_p231_076_mic2.wav" controls preload></audio> |<audio src="demo_p231/mandarin/Source/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/Original/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/DeployVC/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/FACodec/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/DDDM_VC/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/QuickVC/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/DiffVC/481_0600.wav" controls preload></audio> | <audio src="demo_p231/mandarin/VQMIVC/481_0600.wav" controls preload></audio> |
   |--- | --- | --- | --- | --- | --- | --- | --- | --- | --- |








 
 