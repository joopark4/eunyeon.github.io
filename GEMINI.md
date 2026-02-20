# 🚀 EunYeon.io Portfolio - Product Requirements Document (PRD) & Guide

이 문서는 `EunYeon` 개발자 포트폴리오 사이트 구조와 유지보수 가이드를 담고 있는 상세 명세서입니다. 앞으로 새로운 프로젝트(포스트)를 추가하거나 사이트를 관리할 때 이 문서를 기준으로 작업합니다.

---

## 1. 프로젝트 개요 (Overview)
- **사이트 이름:** EunYeon
- **설명:** 주요 프로젝트 (Main Projects) 및 릴리즈 버전을 소개하고, 필요 시 데모 파일(ipa, apk 등)의 다운로드 링크를 제공하는 개인 기술 포트폴리오 웹사이트입니다.
- **배포 환경:** GitHub Pages (무료 호스팅)
- **자동화:** GitHub Actions를 사용하여 `main` 브랜치에 코드가 푸시되면 자동으로 빌드 및 배포됩니다.
- **주요 기술 블록:** Jekyll 정적 사이트 생성기 (Static Site Generator), Ruby, Bootstrap, Lunr.js (검색 엔진)
- **사용 테마:** [Mediumish Theme for Jekyll](https://github.com/wowthemesnet/mediumish-theme-jekyll) (MIT License 기반 커스텀)

---

## 2. 사이트 주요 변경 사항 이력 (Customizations)
초기 테마 구성에서 포트폴리오 목적에 맞게 다음과 같은 주요 수정이 반영되어 있습니다.

1. **상단 내비게이션:** 불필요한 링크(About, Docs, Github Fork 등) 모두 제거.
2. **브랜딩(Branding):** 
   - `eunyeon.io` 텍스트를 `EunYeon`으로 통일 변경.
   - 좌측 상단 범용 테마 로고(`m`)를 개인 맞춤형 `eY` 골드 로고(`assets/images/logo.png`)로 교체 및 여백 제거(크롭).
   - 브라우저 상단 탭 로고(Favicon) 파일(`assets/images/favicon.png`) 커스텀 로고로 교체 완료.
3. **하단 푸터(Footer):**
   - 뉴스레터(메일 구독 폼) 제거.
   - 카테고리 태그 모음 박스("Explore ->" 섹션) 완전 삭제, 미니멀리즘 유지.
   - 테마 제공자 크레딧(WowThemes.net 링크) 삭제 및 저작권 정보 업데이트(`Copyright © 2026 EunYeon`).
4. **검색 엔진(Lunr.js) 정상화:** 검색창에 키워드 입력 후 `Enter(엔터)` 키를 누르면 정상적으로 검색 결과 모달 창이 동작하도록 이벤트(JS)가 추가 보강되었습니다.
5. **저자 아바타:** 포스트 및 목록 하단에 노출되는 기본 사용자 얼굴 이미지를 귀여운 캐릭터 이미지(`assets/images/avatar.jpg`)로 교체.

---

## 3. 📝 신규 포스트(프로젝트) 작성 가이드

사이트 홈 화면("All Stories" 또는 "Featured")에 새로운 프로젝트를 등록하려면 `_posts` 폴더 안에 마크다운 파일(`.md`)을 생성합니다.

### 3.1 파일 생성 규칙
- 경로: `_posts/` 폴더 안
- 파일명 규칙: `YYYY-MM-DD-포스트-영문-제목.md` 
- 예시: `2026-03-01-my-new-app-release.md`

### 3.2 필수 정보 설정 (Front Matter)
파일의 가장 상단 맨 처음에 아래와 같은 정보(메타 데이터)를 반드시 써야 인식이 됩니다.

```yaml
---
layout: post               # (필수) 화면 레이아웃
title:  "앱 이름 또는 프로젝트 제목"   # (필수) 글 제목
author: joopark4           # (선택) _config.yml에 정의된 작성자 ID
categories: [ iOS, App ]   # (선택) 분류시킬 카테고리
image: assets/images/my-app-thumbnail.jpg   # (필수) 홈 화면에 노출될 썸네일 이미지
featured: true             # (선택) 상단 "Featured(추천글)" 섹션에 띄우고 싶다면 true 로 설정
hidden: true               # (선택) true로 설정하면 임시 저장 글로 처리되어 화면 목록에 아예 안 나옵니다.
---
여기서부터 프로젝트 소개 본문을 마크다운(Markdown) 문법으로 свободно 작성합니다!
```

---

## 4. 🖼 미디어(이미지 및 동영상) 첨부 가이드

포트폴리오는 시각적인 결과물이 중요하므로 아래 가이드를 따라 이미지와 비디오를 쉽게 첨부할 수 있습니다.

### 4.1 이미지 첨부
1. 원하시는 이미지 파일을 복사하여 `assets/images/` 폴더 위치에 넣습니다.
2. 포스트(`.md`) 본문 안에서 이미지를 삽입할 위치에 다음 코드를 적습니다.
```markdown
![이미지 설명(대체 텍스트)](/assets/images/내이미지파일.png)
```

### 4.2 동영상 첨부 (2가지 팁)
동영상은 용량이 매우 크기 때문에 가급적 YouTube나 외부 링크를 사용하는 것이 사이트(GitHub Pages) 트래픽 관리상 좋습니다.

**A. YouTube 링크 삽입 (권장 ⭐)**
유튜브에 데모 영상을 비공개/일부공개로 올린 뒤 공유 코드를 복사해서 포스트에 붙여 넣습니다. 반응형(모바일 최적화)으로 영상이 사이트에 깔끔하게 삽입됩니다.
```html
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/영상고유ID" allowfullscreen></iframe>
</div>
```

**B. 짧은 .mp4 애니메이션 직접 첨부 (가벼운 GIF처럼 쓸 때)**
화면 녹화(10초 내외) 등 용량이 작은 경우, 동영상 파일을 프로젝트 폴더의 `assets/videos/데모영상.mp4` 에 넣고 아래 HTML 태그를 사용합니다. 무음(Muted)으로 자동 재생되어 마치 자연스러운 GIF 이미지처럼 보입니다.
```html
<video width="100%" autoplay loop muted playsinline>
  <source src="/assets/videos/데모영상.mp4" type="video/mp4">
  브라우저가 비디오 태그를 지원하지 않습니다.
</video>
```

---

## 5. 👨‍💻 로컬 개발 및 실시간 미리보기 환경 가이드 (Local Testing)
글을 작성하다가, 실제 인터넷에 푸시(Push)하기 전에 내 로컬 PC에서 디자인을 먼저 확인하고 싶을 때 사용합니다.

### 실행 방법
터미널을 열고 포트폴리오 폴더 (`/Users/cauca-m4/GitHub-Repositories/eunyeon-io/joopark4.github.io`)로 이동하여 아래 명령어를 순서대로 입력합니다.

#### 1. (혹시 Ruby 환경 오류가 날 경우에만) 환경변수 로드
```bash
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
```

#### 2. 로컬 서버 켜기
```bash
bundle exec jekyll serve
```

실행 후 브라우저를 열고 `http://127.0.0.1:4000/` 접속하면, 현재 내가 작성 중인 파일들이 그대로 화면에 실시간으로 표시됩니다. 수정을 마치면 터미널에서 `Ctrl + C`를 눌러 서버를 끕니다.

---

## 6. 데모 파일 (다운로드 링크) 관리
진행하신 프로젝트의 테스트.ipa (iOS 앱 파일)를 배포할 때 유용한 방법입니다.
- **클라우드 활용 방식:** 가장 일반적인 방법입니다. 구글 드라이브(Google Drive)나 드롭박스(Dropbox)에 ipa/앱 파일을 업로드 한 뒤 "공유 링크"를 만들고, 포스트 본문에 일반 링크 처리합니다.
  ```markdown
  📥 [iOS 데모 버전(ipa) 외부 링크 다운로드하기](https://구글드라이브.공유.주소.어쩌구)
  ```
- 이 GitHub 저장소 자체에 직접 파일을 올려 배포할 수도 있지만, 용량 관리에 유의하셔야 합니다.(GitHub Pages는 한 파일당 100MB 업로드 한계 권장)

---
*Created and maintained by AI Assistant for EunYeon (2026.02).*
