# Awesome-AdverseWeather-Datasets

**직접 다운로드 가능한 paired 악천후 복원 데이터셋은 총 60여 개로 확인.** Rain 계열이 약 21개, Low-light가 16개, Fog/Haze가 14개, Snow가 6개(단독), Multi-weather가 5개 수준이다.

---

## 1. Rain 계열: 21개 데이터셋

비(rain streak) 제거와 빗방울(raindrop) 제거 분야는 가장 데이터셋이 풍부하다. Synthetic pair가 압도적이며, 최근 Real pair 데이터셋이 빠르게 늘고 있다.

### Rain Streak 제거 데이터셋

| 데이터셋 | 출처 (논문/venue/year) | Synth/Real | 규모 (train/test) | Pair 구성 방식 | 다운로드 | 라이선스 |
|---|---|---|---|---|---|---|
| **Rain100H** | Yang et al., "Deep Joint Rain Detection and Removal from a Single Image," CVPR 2017 / TPAMI 2019 | Synthetic | 1,800 / 100 (480×320) | 5방향 합성 rain streak을 clean 이미지에 중첩 | [DerainZoo GitHub](https://github.com/nnUyi/DerainZoo), [Restormer script](https://github.com/swz30/Restormer) | 연구용 |
| **Rain100L** | 위와 동일 | Synthetic | 200 / 100 (480×320) | 단일 유형 경량 rain streak 합성 | DerainZoo, Restormer script, [Kaggle mirror](https://www.kaggle.com/datasets/adeshpal/rain-100l) | 연구용 |
| **Rain1400 (DDN-Data)** | Fu et al., "Removing Rain from Single Images via a Deep Detail Network," CVPR 2017 / TIP 2017 | Synthetic | 12,600 / 1,400 | 1,000장 clean × 14종 Photoshop rain effect | [GitHub mirror (Git LFS)](https://github.com/jinnovation/rainy-image-dataset), [프로젝트 페이지](https://xueyangfu.github.io/projects/tip2017.html) | 연구용 |
| **Rain12** | Li et al., "Rain Streak Removal Using Layer Priors," CVPR 2016 | Synthetic | 0 / 12 | 단일 rain 패턴 12장 (테스트 전용) | DerainZoo | 연구용 |
| **Rain800** | Zhang & Patel, "Image De-raining Using a Conditional GAN," TCSVT 2020 (arXiv:1701.05957) | Synthetic | 700 / 100 | Photoshop rain 렌더링 | [ID-CGAN GitHub](https://github.com/hezhangsprinter/ID-CGAN) (Google Drive) | 연구용 |
| **Rain1200 (DID-MDN)** | Zhang & Patel, "Density-aware Single Image De-raining using a Multi-stream Dense Network," CVPR 2018 | Synthetic | 12,000 / 1,200 | 3단계 밀도(light/medium/heavy) Photoshop rain, BSD·UCID 기반 | [GitHub](https://github.com/hezhangsprinter/DID-MDN) | 연구용 |
| **Rain13k** | Zamir et al. (MPRNet, CVPR 2021; Restormer, CVPR 2022)에서 통합 | Synthetic | ~13,712 / 다수 테스트셋 | Rain100H+Rain100L+Rain1400+Rain1200+Rain800 통합 | [Restormer download script](https://github.com/swz30/Restormer/blob/main/Deraining/README.md), [MPRNet](https://github.com/swz30/MPRNet) | 연구용 |
| **SPA-Data** | Wang et al., "Spatial Attentive Single-Image Deraining with a High Quality Real Rain Dataset," CVPR 2019 | **Real** | ~29,500 / 1,000 | 실제 비 동영상에서 temporal prior + 수작업으로 clean 배경 추출 | [SPANet GitHub](https://github.com/stevewongv/SPANet) (Baidu Netdisk, key: 4fwo) | 연구용 |
| **GT-RAIN** | Ba et al., "Not Just Streaks: Towards Ground Truth for Single Image Deraining," ECCV 2022 (arXiv:2206.10779) | **Real** | ~31,500 total, 115+ scenes (1920×1080) | YouTube 라이브 스트림에서 비 전후 시간차 촬영, 조명·모션 필터링 | [Kaggle](https://www.kaggle.com/datasets/wxli408/gt-rain), [프로젝트 페이지](https://visual.ee.ucla.edu/gt_rain.htm), [GitHub](https://github.com/UCLA-VMG/GT-RAIN) | 연구용 |
| **RealRain-1k** | Li et al., "Toward Real-world Single Image Deraining: A New Benchmark and Beyond," arXiv:2206.05514, 2022 | **Real** | 1,120 pairs (고해상도) | 실제 비 동영상에서 밀도 제어 필터링으로 자동 생성 | [GitHub → OneDrive](https://github.com/hiker-lw/RealRain-1k) | 연구용 |
| **SynRain-13k** | 위와 동일 논문 | Synthetic (실제 rain layer 활용) | ~13,000 pairs | RealRain-1k에서 추출한 실제 rain streak layer를 자연 이미지에 합성 | 위와 동일 OneDrive | 연구용 |
| **HeavyRain / Outdoor-Rain** | Li et al., "Heavy Rain Image Restoration: Integrating Physics Model and Conditional Adversarial Learning," CVPR 2019 | Synthetic | ~9,000 / 750 | 물리 기반 depth-dependent rain streak + rain accumulation + veiling 효과 | [GitHub](https://github.com/liruoteng/HeavyRainRemoval), AllWeather에 포함 | 연구용 |
| **LHP-Rain** | Guo et al., "From Sky to the Ground: A Large-scale Benchmark and Simple Baseline Towards Real Rain Removal," ICCV 2023 | **Real** | 3,000 시퀀스, ~100만 프레임 (1920×1080) | 실제 비 동영상에서 low-rank tensor recovery로 배경 분리 | [GitHub](https://github.com/yunguo224/LHP-Rain) (프로젝트 페이지 링크) | 연구용 |
| **SyRa** | Jaewoong et al., "Synthesized Rain Images for Deraining Algorithms," Neurocomputing 2022 | Synthetic (GAN) | 50,000 / 5,000 | GAN 기반 합성 rain 이미지 | [GitHub 직접 다운로드](https://github.com/jaewoong1/SyRa-Synthesized_Rain_dataset) | 연구용 |
| **GTAV-NightRain** | Zhang et al., "Learning Rain Location Prior for Nighttime Deraining," ICCV 2023 (arXiv:2210.04708) | Synthetic (게임 엔진) | 5,000 / 500 (1920×1080) | GTAV 게임 엔진으로 야간 비 장면 렌더링 | [GitHub → Kaggle](https://github.com/zkawfanx/RLP) | MIT |

### Raindrop(빗방울) 제거 데이터셋

| 데이터셋 | 출처 | Synth/Real | 규모 | Pair 구성 방식 | 다운로드 | 라이선스 |
|---|---|---|---|---|---|---|
| **RainDrop (Qian et al.)** | Qian et al., "Attentive GAN for Raindrop Removal from A Single Image," CVPR 2018 (arXiv:1711.10098) | **Real** | 861 train / 307 test (720×480) | 유리에 물방울 분사 후 동일 장면 촬영 (with/without drops) | [Google Drive](https://drive.google.com/open?id=1e7R76s6vwUJxILOcAsthgDLPSnOrQ49K), [GitHub](https://github.com/rui1996/DeRaindrop) | 연구용 |
| **Raindrop Clarity** | Jin et al., "Raindrop Clarity: A Dual-Focused Dataset for Day and Night Raindrop Removal," ECCV 2024 (arXiv:2407.16957) | **Real** | ~14,139 train / 731 test | 주간+야간 유리 표면 빗방울 촬영, raindrop-focused와 background-focused 동시 제공 | [GitHub](https://github.com/jinyeying/RaindropClarity) | 연구용 |
| **UAV-Rain1k** | Chen et al., "UAV-Rain1k: A Benchmark for Raindrop Removal from UAV Aerial Imagery," arXiv:2402.05773, 2024 | Synthetic (Blender) | 800 / 220 (~1500×1000) | Blender로 모델링한 raindrop 형상을 실제 UAV 배경에 합성 | [GitHub](https://github.com/cschenxiang/UAV-Rain1k) | 연구용 |

### Rain Streak + Raindrop 복합 데이터셋

| 데이터셋 | 출처 | Synth/Real | 규모 | Pair 구성 방식 | 다운로드 | 라이선스 |
|---|---|---|---|---|---|---|
| **RainDS** | Quan et al., "Removing Raindrops and Rain Streaks in One Go," CVPR 2021 | Both | Real: 248 quadruplets / Syn: 별도 | 실제 촬영: streak-only, drop-only, 복합, clean 4종 세트 | [Google Drive](https://drive.google.com/file/d/12yN6avKi4Tkrnqa3sMUmyyf4FET9npOT/view), [GitHub](https://github.com/Songforrr/RainDS_CCN) | 연구용 |
| **MPID** | Li et al., "Single Image Deraining: A Comprehensive Benchmark Analysis," CVPR 2019 | Both | 다수 서브셋 (streak/drop/mist × synth/real) | Synthetic: rain 렌더링, Real: 인터넷·카메라 수집 | [DerainZoo 링크](https://github.com/nnUyi/DerainZoo) | 연구용 |
| **SPAC-CNN** | Chen et al., "Robust Video Content Alignment and Compensation for Rain Removal in a CNN Framework," CVPR 2018 | Both (video) | 비디오 클립 다수 | Adobe After Effect rain 합성(synthetic) + 실제 비 촬영(real) | [GitHub](https://github.com/hotndy/SPAC-SupplementaryMaterials) | 연구용 |

**Rain 계열 핵심 다운로드 허브**: [DerainZoo](https://github.com/nnUyi/DerainZoo)에서 대부분의 rain 데이터셋 링크를 통합 제공하며, [Restormer repo](https://github.com/swz30/Restormer)의 download script로 Rain13k를 일괄 다운로드할 수 있다.

---

## 2. Fog/Haze 계열: 14개 데이터셋

Dehazing 분야는 RESIDE 벤치마크가 사실상 표준이며, 최근 **실제 연무기(haze machine)**로 촬영한 real pair 데이터셋이 주류로 부상하고 있다.

### RESIDE 벤치마크 패밀리

| 서브셋 | Synth/Real | 규모 | Pair 여부 | 구성 방식 | 다운로드 |
|---|---|---|---|---|---|
| **RESIDE-ITS** (Indoor Training Set) | Synthetic | 13,990 hazy (1,399 clean × 10 조건, ~640×480) | ✅ Paired | NYU Depth V2 실내 이미지에 ASM 기반 haze 합성 | [Dropbox](https://bit.ly/3iwHmh0), [Kaggle](https://www.kaggle.com/datasets/balraj98/indoor-training-set-its-residestandard) |
| **RESIDE-OTS** (Outdoor Training Set) | Synthetic | ~313,950 hazy (8,970 clean × 35 조건) | ✅ Paired | 실외 이미지에 추정 depth map 기반 ASM haze 합성 | [Dropbox](https://bit.ly/3k8a0Gf), Baidu (pw: w54h) |
| **RESIDE-SOTS** (Testing Set) | Synthetic | 500 indoor + 500 outdoor | ✅ Paired | ITS/OTS와 동일 방식 (테스트 전용) | [Dropbox](https://bit.ly/2XZH498), [Kaggle](https://www.kaggle.com/datasets/balraj98/synthetic-objective-testing-set-sots-reside) |
| **RESIDE-HSTS** | Hybrid | 20장 (10 synthetic + 10 real) | ✅ Paired | 합성+실제 혼합 (테스트 전용) | [Dropbox](https://bit.ly/394pcAm) |
| **RESIDE-RTTS** | Real | 4,322장 (VOC 어노테이션) | ❌ **Unpaired** | 실제 안개 이미지, GT 없음 (task-driven 평가용) | [Dropbox](https://bit.ly/3c4gl3z) |

RESIDE의 공식 페이지는 [sites.google.com/view/reside-dehaze-datasets](https://sites.google.com/view/reside-dehaze-datasets/reside-standard)이며, 논문은 Li et al., "Benchmarking Single-Image Dehazing and Beyond," IEEE TIP 2019 (arXiv:1712.04143)이다. 모든 서브셋이 **Dropbox 공개 링크**로 직접 다운로드 가능하다.

### Real Haze 데이터셋 (연무기 촬영)

Ancuti 연구팀(UPT Romania / ETH Zurich)이 NTIRE Challenge 시리즈를 통해 공개한 실제 안개 데이터셋들이 이 분야의 핵심 real-world 벤치마크다. 전문 **연무기(haze machine)**로 실외·실내에 실제 안개를 생성하고 동일 카메라 세팅으로 haze/clean 쌍을 촬영했다.

| 데이터셋 | 출처 | 환경 | 규모 | 다운로드 |
|---|---|---|---|---|
| **O-Haze** | Ancuti et al., CVPR NTIRE Workshop 2018 | 실외, 균질 안개 | 45 pairs (고해상도) | [ETH 직접 다운로드](https://data.vision.ee.ethz.ch/cvl/ntire18/o-haze/) |
| **I-Haze** | Ancuti et al., ACIVS 2018 | 실내, 균질 안개 | 35 pairs (고해상도) | [ETH 직접 다운로드](https://data.vision.ee.ethz.ch/cvl/ntire18/i-haze/) |
| **Dense-Haze** | Ancuti et al., IEEE ICIP 2019 | 실외, 고밀도 균질 안개 | 55 pairs | [ETH 직접 다운로드](https://data.vision.ee.ethz.ch/cvl/ntire19/dense-haze/), [Kaggle](https://www.kaggle.com/datasets/rajat95gupta/hazing-images-dataset-cvpr-2019) |
| **NH-Haze** | Ancuti et al., CVPR NTIRE Workshop 2020 | 실외, **비균질** 안개 (팬 사용) | 55 pairs | [ETH 직접 zip](https://data.vision.ee.ethz.ch/cvl/ntire20/nh-haze/files/NH-HAZE.zip) |

위 네 데이터셋 모두 **ETH 서버에서 로그인 없이 직접 다운로드** 가능하며, 연구 목적 인용 조건으로 무료 사용할 수 있다. 규모는 작지만(35–55쌍) 실제 안개 paired 데이터로서 매우 높은 가치를 지닌다.

### 기타 Haze 데이터셋

| 데이터셋 | 출처 | Synth/Real | 규모 | Pair 구성 방식 | 다운로드 | 비고 |
|---|---|---|---|---|---|---|
| **D-Hazy** | Ancuti et al., "D-Hazy: A Dataset to Evaluate Quantitatively Dehazing Algorithms," ICIP 2016 | Synthetic | ~1,400+ pairs | Middlebury·NYU-Depth V2의 depth map으로 Koschmieder 모델 haze 합성 | [공식 페이지](http://www.meo.etc.upt.ro/AncutiProjectPages/D_Hazzy_ICIP2016/) | 연구용 |
| **Haze4K** | Song et al., "From Synthetic to Real: Image Dehazing Collaborating with Unlabeled Real Data" (DMT-Net), arXiv:2108.02934 | Synthetic | 3,000 train / 1,000 test | Depth 기반 ASM 합성 | [GitHub](https://github.com/liuye123321/DMT-Net) (Baidu Pan, pw: cmmr) | ⚠️ Baidu 전용 |
| **REVIDE** | Zhang et al., "Learning To Restore Hazy Video: A New Real-World Dataset and A New Method," CVPR 2021 | **Real** | ~1,981 프레임 (실내) | 맞춤형 촬영 시스템으로 동일 장면 haze/clean 2회 촬영 | [GitHub → Google Drive](https://github.com/BookerDeWitt/REVIDE_Dataset) | 연구용, 비디오 |
| **BeDDE** | Zhao et al., "Dehazing Evaluation: Real-World Benchmark Datasets, Criteria, and Baselines," IEEE TIP 2020 | **Real** | 208 pairs | 고정 카메라로 안개/맑은 날 동일 장면 촬영, ROI 정합 | [GitHub → Google Drive](https://github.com/xiaofeng94/BeDDE-for-defogging) | 주로 평가용 |
| **LMHaze** | Zhang et al., "LMHaze: Intensity-aware Image Dehazing with a Large-scale Multi-intensity Real Haze Dataset," ACM MM Asia 2024 (arXiv:2410.16095) | **Real** | **5,000+ pairs** (고해상도) | 전문 연무기로 다단계 농도별 실내+실외 촬영, 최대 규모 real dehazing 데이터셋 | [GitHub → Google Drive](https://github.com/wangzrk/LMHaze) | Apache 2.0 |
| **RICE** | Luo et al., "RICE: A Dataset and Baseline for Cloud Removal in Remote Sensing Images" | **Real** (원격탐사) | RICE-I: 500쌍 / RICE-II: 736쌍 (512×512) | Google Earth Engine에서 동일 지점 구름 유무 촬영 | [GitHub](https://github.com/BUPTLdy/RICE_DATASET) | 원격탐사 특화 |

**LMHaze**는 2024년 공개된 데이터셋으로, **5,000쌍 이상**의 실제 안개 paired 이미지를 제공하며 이는 real-world dehazing 데이터셋 중 최대 규모다. Foggy Cityscapes는 무료 Cityscapes 계정 등록이 필요하므로 경계선 사례로 분류했다.

---

## 3. Snow 계열: 9개 데이터셋

Snow 제거 분야는 다른 악천후에 비해 데이터셋이 가장 적다. 대부분 Photoshop 기반 합성이며, 실사 paired 데이터는 극히 드물다.

| 데이터셋 | 출처 | Synth/Real | 규모 | Pair 구성 방식 | 다운로드 | 라이선스 |
|---|---|---|---|---|---|---|
| **Snow100K** | Liu et al., "DesnowNet: Context-Aware Deep Network for Snow Removal," IEEE TIP 2018 (arXiv:1708.04512) | Synthetic | 50,000 train / 50,000 test (S/M/L 3서브셋, max 640px) | Photoshop 기반 반투명·불투명 눈 입자 합성 (Flickr clean 이미지 기반) | [프로젝트 페이지 → Google Drive](https://sites.google.com/view/yunfuliu/desnownet) (train 7.8GB, test 7.8GB) | 미명시 |
| **CSD** | Chen et al., "ALL Snow Removed: Single Image Desnowing Algorithm Using Hierarchical Dual-Tree Complex Wavelet Representation and Contradict Channel Loss," ICCV 2021 | Synthetic | 8,000 train / 2,000 test (480×640) | Photoshop snow streak + Koschmieder veiling + Gaussian blur | [GitHub → Google Drive](https://github.com/weitingchen83/ICCV2021-Single-Image-Desnowing-HDCWNet) | 미명시 |
| **SRRS** | Chen et al., "JSTASR: Joint Size and Transparency-Aware Snow Removal Algorithm Based on Modified Partial Convolution and Veiling Effect Removal," ECCV 2020 | Synthetic | ~15,000 train / ~1,000 test | Koschmieder veiling effect + Photoshop snow streak 합성 | [GitHub → Google Drive](https://github.com/weitingchen83/JSTASR-DesnowNet-ECCV-2020) | 미명시 |
| **SnowKITTI2012** | Zhang et al., "Deep Dense Multi-scale Network for Snow Removal Using Semantic and Depth Priors," IEEE TIP 2021 | Synthetic | KITTI 2012 기반 × 3 레벨 (light/medium/heavy) | KITTI 이미지 위에 3단계 밀도 눈 입자 합성 | [Google Drive](https://drive.google.com/file/d/1TB1WC60ZJvazepdvay18dCRr0yVLU6bH/view) | 미명시 |
| **SnowCityScapes** | 위와 동일 논문 | Synthetic | Cityscapes 기반 × 3 레벨 | Cityscapes 이미지 위에 동일 방식 눈 합성 | [Google Drive](https://drive.google.com/file/d/1E6iXFV6K5UJ4Mrqer17v6KsHhQOFvjtO/view) | Cityscapes 라이선스 |
| **RVSD** | Chen et al., "Snow Removal in Video: A New Dataset and A Novel Method," ICCV 2023 | Synthetic (UE5) | 110 비디오 쌍 | Unreal Engine 5로 snow+haze 렌더링 | [GitHub → Google Drive](https://github.com/haoyuc/VideoDesnowing) | 연구용 |
| **RealSnow** | Zhu et al., "WGWS-Net," WGWS-Net GitHub | **Real** | 소규모 | 배경 고정 동영상에서 눈 전후 temporal pair 추출 | [GitHub](https://github.com/zhuyr97/WGWS-Net) (Baidu Pan, pw: cvpr) | ⚠️ Baidu 전용 |
| **WeatherStream (snow 서브셋)** | Zhang et al., CVPR 2023 (아래 Multi-weather 참조) | **Real** | 대규모 | 웹캠 시계열에서 눈/clean 자동 pair 추출 | [Google Drive](https://drive.google.com/drive/folders/12Z9rBSTs0PPNHLieyU2vnCTzR6fOFLrT) | 연구용 |
| **CDD-11 (snow 서브셋)** | Guo et al., ECCV 2024 (아래 Multi-weather 참조) | Synthetic | CDD-11의 snow/low_snow/haze_snow/low_haze_snow 4종 포함 | 물리 기반 복합 열화 합성 | [Hugging Face](https://huggingface.co/datasets/gy65896/CDD-11) | 미명시 |

Snow 분야의 핵심 다운로드 허브는 [SnowFormer GitHub](https://github.com/Ephemeral182/SnowFormer)로, Baidu Pan(pw: ephe)을 통해 CSD, SRRS, Snow100K, SnowKITTI, SnowCityScapes를 일괄 다운로드할 수 있다. **Snow100K**이 10만 쌍으로 압도적 규모이며, 대부분의 desnowing 논문에서 표준 벤치마크로 사용된다.

---

## 4. Low-light/Night 계열: 16개 데이터셋

저조도 향상 분야는 실제 촬영(노출 시간 변경) 기반 real pair가 주류를 이루며, RAW 센서 데이터를 제공하는 데이터셋이 큰 비중을 차지한다.

### 주요 Paired 학습 데이터셋

| 데이터셋 | 출처 | Synth/Real | 규모 | Pair 구성 방식 | 다운로드 | 라이선스 |
|---|---|---|---|---|---|---|
| **LOL** | Wei et al., "Deep Retinex Decomposition for Low-Light Enhancement," BMVC 2018 | **Real** | 485 train / 15 test (400×600) | 동일 장면 노출 시간·ISO 변경으로 저조도/정상 쌍 촬영 | [프로젝트 페이지 → Google Drive](https://daooshee.github.io/BMVC2018website/), Kaggle, Hugging Face | 연구용 |
| **LOLv2-Real** | Yang et al., "Sparse Gradient Regularized Deep Retinex Network for Robust Low-Light Image Enhancement," IEEE TIP 2021 | **Real** | 689 train / 100 test (~400×600) | LOL과 동일 방식, 더 다양한 장면 | [GitHub → Google Drive](https://github.com/flyywh/CVPR-2020-Semi-Low-Light) | 연구용 |
| **LOLv2-Synthetic** | 위와 동일 | Synthetic | ~900 train / 100 test | 정상 이미지에 합성 어두움+노이즈 적용 | 위와 동일 | 연구용 |
| **VE-LOL** | Liu et al., "Benchmarking Low-Light Image Enhancement and Beyond," IJCV 2021 | **Real** | VE-LOL-L (저수준 pair) + VE-LOL-H (얼굴 검출 어노테이션) | 다양한 노출 설정 실제 촬영 + 얼굴 BB 어노테이션 | [Dropbox + Baiduyun](https://flyywh.github.io/IJCV2021LowLight_VELOL/) | 연구용 |
| **SID-Sony** | Chen et al., "Learning to See in the Dark," CVPR 2018 | **Real** (RAW) | ~2,697 RAW 이미지 (Sony α7S II, 4240×2832) | 동일 장면 단·장노출 RAW pair (1/30s ↔ 10–30s), 극저조도 0.03–5 lux | [GitHub → Google Drive](https://github.com/cchen156/Learning-to-See-in-the-Dark) (25GB) | **MIT** |
| **SID-Fuji** | 위와 동일 | **Real** (RAW) | ~2,397 RAW 이미지 (Fujifilm X-T2 X-Trans, 6000×4000) | 위와 동일 방식 | 위와 동일 (52GB) | **MIT** |
| **SMID** | Jiang et al., "Learning to See Moving Objects in the Dark," ICCV 2019 | **Real** (RAW video) | 179 비디오 쌍, 35,800 프레임 (3672×5496) | 이중 카메라+ND 필터로 동일 동적 장면의 밝은/어두운 비디오 동시 촬영 | [GitHub → Google Drive](https://github.com/JIA-Lab-research/SDSD), Baidu (pw: btux) | 연구용 |
| **SDSD** | Wang et al., "Seeing Dynamic Scene in the Dark: High-Quality Video Dataset with Mechatronic Alignment," ICCV 2021 | **Real** (video) | 150 비디오 × ~250프레임, indoor+outdoor (1920×1080) | 기계식 동기화 시스템으로 동적 장면 저조도/정상 비디오 pair 정밀 촬영 | [GitHub → Google Drive](https://github.com/JIA-Lab-research/SDSD) | 연구용 |
| **SICE** | Cai et al., "Learning a Deep Single Image Contrast Enhancer from Multi-Exposure Images," IEEE TIP 2018 | **Real** (다중 노출) | 589 시퀀스, 4,413장 (고해상도) | 삼각대 고정 다중 노출 시퀀스 촬영, 13종 fusion/HDR 알고리즘 중 최고 품질을 GT로 선정 | [GitHub](https://github.com/csjcai/SICE) (Baidu Yun + Google Drive) | 연구용 |
| **MIT-Adobe FiveK** | Bychkovsky et al., "Learning Photographic Global Tonal Adjustment with a Database of Input/Output Image Pairs," CVPR 2011 | **Real** | 5,000 RAW + Expert A–E 보정 (~50GB) | 5명의 전문 사진가가 Adobe Lightroom으로 RAW 이미지 보정, Expert C가 LLIE 표준 GT | [MIT 직접 다운로드](https://data.csail.mit.edu/graphics/fivek/), Hugging Face, Kaggle | 연구+상업 이중 라이선스 |
| **LOL-Blur** | Zhou et al., "LEDNet: Joint Low-light Enhancement and Deblurring in the Dark," ECCV 2022 | Synthetic | 10,200 train / 1,800 test | 노출 시뮬레이션 + 노이즈 주입 + 모션 블러 합성 + ISP + 감마 보정 파이프라인 | [GitHub → Google Drive](https://github.com/sczhou/LEDNet), Baidu (pw: dz6u) | 연구용 |
| **ELD** | Wei et al., "A Physics-based Noise Formation Model for Extreme Low-light Raw Denoising," CVPR 2020 Oral / TPAMI 2021 | **Real** (RAW) | 10 scenes × 4 cameras × 3 ISO × 2 factors = 240 pairs | 기본 ISO 정상 노출 참조 vs. ×100/×200 감소 노출 RAW pair | [GitHub → Google Drive](https://github.com/Vandermode/ELD), Baidu (pw: 0lby) | 평가 전용 |
| **UHD-LOL4K** | Wang et al., "Ultra-High-Definition Low-Light Image Enhancement: A Benchmark and Transformer-Based Method," AAAI 2023 | **Real** | 5,999 pairs (3840×2160) | UHD 해상도 다중 노출 실제 촬영 | [GitHub → OneDrive](https://github.com/TaoWangzj/LLFormer), Baidu | 비상업 연구용 |
| **UHD-LOL8K** | 위와 동일 | **Real** | 2,966 pairs (7680×4320) | 위와 동일, 8K 해상도 | 위와 동일 | 비상업 연구용 |
| **UHD-LL (UHDFour)** | Li et al., UHDFour 프로젝트 | **Real** | 2,000 train / 150 test (960×540 ~ UHD) | 다중 노출 UHD 저조도 이미지 | [GitHub → Google Drive](https://github.com/Li-Chongyi/UHDFour_code), Baidu (pw: 1234) | 연구용 |
| **RELLISUR** | Aakerberg et al., "RELLISUR: A Real Low-Light Image Super-Resolution Dataset," NeurIPS 2021 Datasets Track | **Real** | 12,750 paired (850 시퀀스 × 3 스케일 × 5 노출) | Canon 카메라로 -5EV~0EV 다양한 노출+해상도 실제 촬영 | [Zenodo](https://zenodo.org/records/5234969) | 연구용 |

### Unpaired / 평가 전용 (참고)

**DICM** (44장), **NPE**, **VV**, **LIME** (10장), **MEF**는 모두 GT가 없는 unpaired 평가 전용 이미지셋이다. [Retinexformer repo](https://github.com/caiyuanhao1998/Retinexformer)에서 이들의 통합 다운로드 링크를 제공한다. **ExDark** (7,363장)은 객체 검출 전용으로 paired 복원 GT가 없다.

---

## 5. Multi-weather(복합 악천후) 계열: 5개 데이터셋

최근 "all-in-one" 복원 연구가 급증하면서 여러 악천후를 하나로 묶은 데이터셋이 등장했다. 대부분 기존 단일 악천후 데이터셋의 **조합**이지만, CDD-11처럼 **동시 복합 열화(composite degradation)**를 제공하는 고유 데이터셋도 있다.

| 데이터셋 | 출처 | 포함 악천후 | Synth/Real | 규모 | 구성 | 다운로드 |
|---|---|---|---|---|---|---|
| **AllWeather** | Valanarasu et al., "TransWeather: Transformer-based Restoration of Images Degraded by Adverse Weather Conditions," CVPR 2022 (arXiv:2111.14813) | Rain+Haze, Raindrop, Snow | Synthetic | 18,069 train (Snow100K 9,001 + RainDrop 818 + Outdoor-Rain 8,250) | Snow100K + RainDrop + Outdoor-Rain의 서브셋 조합 | [GitHub → Google Drive](https://github.com/jeya-maria-jose/TransWeather) |
| **CDD-11** | Guo et al., "OneRestore: A Universal Restoration Framework for Composite Degradation," ECCV 2024 (arXiv:2407.04621) | **11종 복합**: low, haze, rain, snow, low+haze, low+rain, low+snow, haze+rain, haze+snow, low+haze+rain, low+haze+snow | Synthetic | 13,013 train / 2,200 test (1,383 clean × 11 열화 유형) | 물리 기반 모델로 depth·light·rain·snow mask를 동시 적용하여 **복합 열화** 합성 | [GitHub → OneDrive](https://github.com/gy65896/OneRestore), [Hugging Face](https://huggingface.co/datasets/gy65896/CDD-11) |
| **WeatherStream** | Zhang et al., "WeatherStream: Light Transport Automation of Single Image Deweathering," CVPR 2023 | Rain, Snow, Rain+Fog | **Real** | **174,000+ pairs**, 424 scenes | 전 세계 웹캠에서 light-transport 물리 기반 자동 파이프라인으로 악천후/clean pair 추출 (99.6% 기각률) | [Google Drive](https://drive.google.com/drive/folders/12Z9rBSTs0PPNHLieyU2vnCTzR6fOFLrT), [GitHub](https://github.com/UCLA-VMG/WeatherStream) |
| **BID (Task III)** | Han et al., "Blind Image Decomposition," ECCV 2022 | Rain+Haze 결합 | Mixed | 다수 서브셋 | 다양한 blind decomposition 태스크용 paired 데이터 | [Google Drive](https://drive.google.com/drive/folders/1wUUKTiRAGVvelarhsjmZZ_1iBdBaM6Ka), [GitHub](https://github.com/JunlinHan/BID) |
| **WeatherBench (IR)** | Guan et al., "WeatherBench: A Real-World Benchmark Dataset for All-in-One Adverse Weather Image Restoration," ACM MM 2025 (arXiv:2509.11642) | Rain, Snow, Haze | **Real** | 대규모 (주간+야간) | 물리적 날씨 생성기(haze/rain/snow generator)와 Sony ILCE-7M3 카메라로 제어 환경에서 촬영 | [GitHub](https://github.com/guanqiyuan/WeatherBench) |

**AllWeather**는 TransWeather(CVPR 2022) 이후 WeatherDiffusion, WeatherFormer, GridFormer, PromptIR 등 수십 편의 all-in-one 논문이 동일하게 사용하는 사실상의 표준 multi-weather 학습셋이다. **CDD-11**은 단순 혼합이 아닌 동시 복합 열화를 제공한다는 점에서 차별화된다. **WeatherStream**은 **17만 쌍 이상**의 real-world 데이터를 보유한 최대 규모 실사 multi-weather 데이터셋이다.

---

## 데이터셋 선택 가이드와 실무 권장사항

연구 목적에 따른 데이터셋 선택은 다음 기준으로 판단하는 것이 효과적이다.

**대규모 학습에 적합한 데이터셋**은 Rain13k(~13,700쌍), RESIDE-OTS(~31만), Snow100K(10만), SID(~5,000 RAW), WeatherStream(17만+)이다. 이들은 딥러닝 모델 학습에 충분한 규모를 제공한다.

**Real-world 일반화 성능 검증**에는 GT-RAIN, LHP-Rain, RealRain-1k(비), LMHaze(안개), WeatherStream(복합), SID/SMID/SDSD(저조도)가 핵심이다. 합성 데이터로 학습 후 이들 real 데이터셋에서 평가하는 것이 최근 표준 프로토콜이다.

**All-in-one 모델 학습**에는 AllWeather 또는 CDD-11이 즉시 사용 가능하다. AllWeather는 기존 논문과의 공정 비교에, CDD-11은 복합 열화 시나리오 연구에 각각 적합하다.

다운로드 접근성 측면에서 **Baidu Pan 전용** 데이터셋(Haze4K, LSRW, RealSnow 등)은 중국 외 지역에서 접근이 어려울 수 있다. 대안으로 Google Drive·Kaggle·Hugging Face 미러를 먼저 확인하거나, 동일 용도의 다른 데이터셋을 선택하는 것이 실용적이다.

## 결론

이 조사에서 확인한 **즉시 다운로드 가능한 paired 학습 데이터셋**은 Rain 21개, Fog/Haze 14개(RESIDE 5서브셋 포함), Snow 9개, Low-light 16개, Multi-weather 5개로 총 약 **60여 개**에 달한다. 핵심적 발견은 세 가지다. 첫째, 2022년 이후 real-world paired 데이터셋이 급증하여(GT-RAIN, LMHaze, WeatherStream, WeatherBench 등) 합성-실사 간 도메인 갭 문제를 직접 해결할 수 있게 되었다. 둘째, CDD-11과 같은 **복합 열화** 데이터셋의 등장은 단일 악천후 모델에서 통합 복원 모델로의 패러다임 전환을 가속하고 있다. 셋째, 대부분의 데이터셋이 GitHub·Google Drive를 통해 공개되어 있어 재현성이 높지만, Baidu Pan 전용이나 링크 만료 등의 문제가 일부 존재하므로 연구 착수 전 다운로드 가능 여부를 반드시 재확인해야 한다.
