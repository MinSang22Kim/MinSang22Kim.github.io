# MinSang Tech Archive

Hugo 기반 개인 기술 블로그입니다. 노션에서 작성한 마크다운 문서를 이미지 포함하여 장기 아카이빙하고 SEO 친화적으로 관리하는 것을 목표로 합니다.

## 기술 스택

- **Static Site Generator**: Hugo
- **Theme**: PaperMod
- **Hosting**: GitHub Pages


## 글 작성 방법

> **중요**: Hugo는 정적 사이트 생성기입니다. 웹 UI가 없으므로 터미널 또는 에디터로 직접 파일을 생성합니다.

### 방법 1: Hugo 명령어 사용 (권장)

```bash
# 명령어로 새 글 생성
hugo new content/posts/my-first-post.md

# 생성된 파일 편집
code content/posts/my-first-post.md  # VS Code
```

### 방법 2: 직접 파일 생성

```bash
# 파일을 직접 만들어도 됩니다
touch content/posts/my-first-post.md
```

### Front Matter 작성 예시

```yaml
---
title: "Spring Boot 트랜잭션 정리"
description: "Spring Boot 트랜잭션 전파 방식과 실무 주의사항"
date: 2024-12-21
categories: ["Spring"]
tags: ["Spring Boot", "트랜잭션"]
draft: false
---

# 본문 작성

마크다운으로 자유롭게 작성하세요.
```

### 이미지 추가

```bash
# 1. 이미지 폴더 생성
mkdir -p static/images/posts/my-first-post

# 2. 이미지 파일 복사
cp ~/Downloads/diagram.png static/images/posts/my-first-post/

# 3. 마크다운에서 참조
![다이어그램](/images/posts/my-first-post/diagram.png)
```

## 프로젝트 구조

```
.
├── archetypes/          # 글 템플릿 (hugo new 시 사용)
│   └── default.md       # 기본 템플릿
├── content/             # 마크다운 글
│   ├── posts/           # 블로그 포스트
│   └── archives.md      # 전체 글 목록 페이지
├── static/              # 정적 파일 (이미지 등)
│   └── images/
│       ├── posts/       # 포스트별 이미지
│       └── common/      # 공통 이미지
├── themes/              # 테마 (건드리지 않음)
│   └── PaperMod/        # PaperMod 테마
├── hugo.toml            # Hugo 설정 파일
├── CLAUDE.md            # 작성 가이드
└── README.md            # 이 파일

필요시 생성되는 폴더:
├── layouts/             # 테마 레이아웃 오버라이드
├── assets/              # 커스텀 CSS/JS
└── public/              # 빌드 결과물 (Git 무시)
```

## 작성 원칙

자세한 작성 원칙은 [CLAUDE.md](./CLAUDE.md)를 참고하세요.

- 파일명(slug)은 영문 소문자 kebab-case
- 제목은 한국어, slug는 영문
- 카테고리는 자유롭게 추가 가능
- 이미지는 static/images/ 아래에서만 관리
- HTML 직접 작성 지양
