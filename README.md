# [MinSang Tech Archive](https://minsang22kim.github.io)

Hugo 기반 개인 기술 블로그입니다.<br>
노션 글들을 조금씩 이주하여 관리하려고 합니다.

## 1. 기술 스택

- Static Site Generator: Hugo
- Theme: PaperMod
- Hosting: GitHub Pages

## 2. 글 작성 방법

### 2.1 새 글 생성

```bash
hugo new content/posts/example.md
```
또는 에디터에서 직접 파일 생성

### 2.2 Front Matter 및 본문 작성 예시

```yaml
---
# 글 제목
title: "Spring Boot 트랜잭션 정리"

# SEO 설명
description: "Spring Boot 트랜잭션 전파 방식과 실무 주의사항"

# 작성 날짜 (비워두면 오늘 날짜)
date: 2024-12-21

# 카테고리
categories: ["Spring"]

# 태그
tags: ["Spring Boot", "트랜잭션"]

# false여야 공개
draft: false
---

# Hello
마크다운으로 본문을 자유롭게 작성
```

### 2.3 이미지 추가 예시

```bash
mkdir -p static/images/posts/hello
cp ~/Downloads/diagram.png static/images/posts/hello/
```
또는 에디터에서 직접 이미지 추가

### 2.4 이미지 사용 예시
```bash
![다이어그램](/images/posts/hello/diagram.png)
```

## 3. 프로젝트 구조

```bash
MinSang22Kim.github.io/
├── archetypes/          # 글 템플릿
│   └── default.md
├── content/             # 마크다운 글
│   ├── posts/
│   └── archives.md
├── static/              # 정적 파일
│   └── images/
│       ├── posts/
│       └── common/
├── themes/              # 테마
│   └── PaperMod/
├── hugo.toml            # Hugo 설정
├── CLAUDE.md            # 작성 가이드
└── README.md            # 이 문서
```

# 4. 작성 원칙 
- 파일명(slug)은 영문 소문자 kebab-case
- 제목(title)은 한국어, slug는 영문
- 카테고리는 Front Matter로 관리
- 이미지는 static/images/ 아래에서만 관리
