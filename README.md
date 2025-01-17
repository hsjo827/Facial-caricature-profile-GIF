# Face Caricature Profile Generator

## Project Overview
GitHub 프로필 등 공개적인 플랫폼에 자신의 증명사진을 올리는 것이 부담스러운 사용자들을 위해, 실제 얼굴 사진을 기반으로 사용자의 특징을 반영한 캐리커처를 생성하고 GIF 애니메이션으로 변환하는 프로젝트입니다.

## Project Structure
```
📦 Face-Caricature-Profile
├── 📂 DiffStyler          # 스타일 변환 구현
├── 📂 Gradio             # WebUI 구현
├── 📂 input              # 입력 이미지 저장
├── 📂 LivePortrait       # 이미지-비디오 변환
├── 📂 results            # 생성 결과물
├── 📂 SAM               # Segment Anything Model
├── 📂 발표자료           # 발표 자료
├── 📂 사진조사           # 연구 자료
├── 📄 Gradio_main.ipynb # Colab 노트북
├── 📄 main.py           # 메인 실행 파일
└── 📄 README.md         # 프로젝트 문서
```

## Technical Process

### 1. Face Detection and Segmentation
- SAM을 사용하여 정밀한 얼굴 마스크 생성
- 스타일 변환을 위한 자동 마스크 선택

### 2. Style Transfer
- DiffStyler를 활용한 예술적 스타일 변환
- 개인의 특징을 유지하면서 예술적 스타일 적용

### 3. Animation Generation
- LivePortrait를 통한 이미지-비디오 변환
- 다양한 감정 표현 가능
- 고품질 GIF 출력

## Installation & Setup

### Prerequites
```bash
torch
torchvision
segment-anything
gradio
```

### Install
1. Git clone
```bash
git clone https://github.com/username/Face-Caricature-Profile.git
```

2. Install
```bash
cd Face-Caricature-Profile

# SAM install
pip install git+https://github.com/facebookresearch/segment-anything.git
pip install gradio

# DiffStyler install
cd DiffStyler
pip install -r requirements.txt
pip install "jax[cuda12_pip]==0.4.23"

# LivePortrait install
cd ../LivePortrait
pip install -r requirements.txt
```

## Usage Guide

### WebUI 사용법
1. Gradio 인터페이스 실행
```bash
python Formula_WebUI.py
```
2. UI에 사진 드래그 앤 드롭
3. 원하는 스타일과 감정 선택
4. 캐리커처 생성 및 다운로드

### 결과 미리보기

| Original | Mask | Style Image | DiffStyler |
|----------|----------|----------|----------|
|<img src="https://github.com/user-attachments/assets/95c76841-a88e-4f27-b022-a750dc66fead" width="710"> | <img src="https://github.com/user-attachments/assets/2b0e063a-2c2f-48bd-9b15-f15edfd482c3" width="800"> | <img src="https://github.com/user-attachments/assets/901b32c6-a187-400c-996f-6820f974cc0c" width="660" > |<img src = "https://github.com/user-attachments/assets/d8ec6390-6463-4aaa-b16e-3688634972c4" width="690"> | 

| Driving Video | LivePortrait Result |
|----------|----------|
|<img src="https://github.com/user-attachments/assets/9788d76b-2067-47f2-a9bd-347152c9b335" height = "500"> | <img src ="https://github.com/user-attachments/assets/ae8b9eff-6a18-4a98-ac39-e471cf25c927" height = "500"> |

| WebUI Interface |
|----------|
|<img src="https://github.com/user-attachments/assets/97057a69-5d6a-4725-b5eb-448a3c9da02d"> |

## Team Information
- **소속**: 국민대학교 AI빅데이터융합경영학과 인공지능 학회 X:AI Advanced Computer Vision Team 1
- **팀원**: 권민지, 김서령, 김진하, 유광열(팀장), 조현식

## Project Duration 
2024.07 ~ 2024.08 (2개월)

## References
- [중간 발표 자료](https://github.com/yugwangyeol/2024_XAI_ADV_CV1_Toyproject/raw/main/발표자료/XAI_CV_Toy_project_중간발표.pdf)
- [최종 발표 자료](https://github.com/yugwangyeol/2024_XAI_ADV_CV1_Toyproject/raw/main/발표자료/XAI_CV_Toy_project_최종발표.pdf)
- [발표 영상](https://youtu.be/act0FJvckIY)

## Citation
```bibtex
@misc{li2024diffstyler,
      title={DiffStyler: Diffusion-based Localized Image Style Transfer}, 
      author={Shaoxu Li},
      year={2024},
      eprint={2403.18461},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```

```bash
@article{kirillov2023segany,
  title={Segment Anything},
  author={Kirillov, Alexander and Mintun, Eric and Ravi, Nikhila and Mao, Hanzi and Rolland, Chloe and Gustafson, Laura and Xiao, Tete and Whitehead, Spencer and Berg, Alexander C. and Lo, Wan-Yen and Doll{\'a}r, Piotr and Girshick, Ross},
  journal={arXiv:2304.02643},
  year={2023}
}
```

```bash
@article{guo2024liveportrait,
  title   = {LivePortrait: Efficient Portrait Animation with Stitching and Retargeting Control},
  author  = {Guo, Jianzhu and Zhang, Dingyun and Liu, Xiaoqiang and Zhong, Zhizhou and Zhang, Yuan and Wan, Pengfei and Zhang, Di},
  journal = {arXiv preprint arXiv:2407.03168},
  year    = {2024}
}
```