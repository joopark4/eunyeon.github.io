---
layout: post
title:  "MyPartnerAI"
author: joopark4
categories: [ macOS, App, Private ]
image: assets/images/mypartnerai-thumb.jpg
featured: true
published: true
---

## 💡 프로젝트 소개 (Overview)

**MyPartnerAI**는 VRM 모델을 기반으로 한 나만의 아바타 AI 비서 앱입니다.

- **지원 API:** Gemini, OpenAI, Claude API 지원
- **로컬 모델:** Ollama 연동을 통한 프라이빗 로컬 모델(On-Device AI) 지원
- **다국어 소통:** 한국어 및 영어 지원

---

## 📥 다운로드 및 설치 가이드 (Releases v0.3.0)

GitHub Release의 단일 파일 2GB 용량 제한으로 인해 설치 프로그램(DMG)을 500MB씩 총 5개 파트로 분할하여 제공하고 있습니다. 
안전하고 정상적인 설치를 위해 아래의 안내를 순서대로 따라주세요.

### 1️⃣ 전체 파트 다운로드
우선, 터미널 병합을 위해 **모든 파트 파일**을 동일한 폴더(예: `Downloads` 폴더)에 다운로드 받아주세요.

- 📦 [MyPartnerAI-0.3.0.dmg.partaa](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.partaa)
- 📦 [MyPartnerAI-0.3.0.dmg.partab](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.partab)
- 📦 [MyPartnerAI-0.3.0.dmg.partac](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.partac)
- 📦 [MyPartnerAI-0.3.0.dmg.partad](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.partad)
- 📦 [MyPartnerAI-0.3.0.dmg.partae](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.partae)

*(💡 추가로, 체크섬 검증을 원하시면 아래의 [sha256 파일](https://github.com/joopark4/MyPartnerAI/releases/download/v0.3.0/MyPartnerAI-0.3.0.dmg.sha256)도 함께 다운로드해 주세요.)*

### 2️⃣ 파일 병합 (터미널)
Mac의 터미널(Terminal) 앱을 열고 다운로드 받은 폴더로 이동한 뒤, 아래 명령어를 입력하여 하나의 구동 가능한 DMG 파일로 합쳐줍니다.

```bash
cat MyPartnerAI-0.3.0.dmg.part* > MyPartnerAI-0.3.0.dmg
```

### 3️⃣ 무결성 검증 (SHA-256 Checksum)
단말기 및 네트워크 환경에 따라 파일 손상이 발생할 수 있으니 가급적이면 병합된 파일의 해시값을 꼭 검증해주세요. 터미널에 아래 명령어를 실행합니다.

```bash
shasum -a 256 MyPartnerAI-0.3.0.dmg
```

**[예상 결과 값]**
`c9fb383b13c15fcea830097f25a68252948c82d944723d6726de33cab0ecb314`
*(출력된 해시값이 위와 동일하다면 손상 없이 다운로드 및 병합이 완료된 것입니다!)*

### 4️⃣ 설치 및 실행
1. 해시값 검증이 완료된 `MyPartnerAI-0.3.0.dmg` 파일을 더블 클릭하여 실행(마운트)합니다.
2. 창이 열리면, **MyPartnerAI 아이콘**을 옆에 있는 **Applications(응용 프로그램)** 폴더로 드래그 앤 드롭하여 설치를 완료합니다.

---
> ⚠️ **주의사항 (Notice):**
> 안전한 배포를 위해 반드시 제공된 Checksum 정보를 대조하여 파일 손상 및 변조 여부를 확인하시기 바랍니다. 애플리케이션 실행 시 경고가 발생한다면 [시스템 설정] -> [개인정보 보호 및 보안]에서 앱 실행을 허용해주세요.
