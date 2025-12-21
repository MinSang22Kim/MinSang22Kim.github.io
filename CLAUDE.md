# Hugo 기반 개인 기술 아카이브 가이드

이 문서는 본 레포지토리에서 작업 시 따라야 할 **최소한의 구조·작성 원칙**을 정의한다.  
본 블로그의 목적은 **노션에서 작성된 마크다운 문서를 이미지 포함하여 장기 아카이빙하고, SEO 친화적으로 관리**하는 것이다.

---

## 1. 기본 방향

- 블로그는 **지식 아카이브** 목적
- 서비스, 사용자 기능, 서버 개념 없음
- 글 작성 시 코딩 불필요 (Markdown만 사용)
- 구조는 단순하게, 확장은 자유롭게
- 과거 글 이주 + 신규 글 혼용 허용

---

## 2. 폴더 구조 (권장 패턴)

```text
.
├─ content/          # 글 (Markdown)
│  └─ {category}/    # 카테고리 (자유롭게 추가)
│     └─ post.md
│
├─ static/           # 정적 자산
│  └─ images/
│     ├─ posts/{slug}/
│     └─ common/
│
├─ layouts/          # Hugo 템플릿
├─ themes/           # PaperMod
└─ hugo.toml

구조 원칙
	•	content/ 하위 폴더 = 카테고리
	•	카테고리는 고정하지 않음 (필요 시 추가)
	•	기존 글을 다른 카테고리로 이동 가능
	•	이미지와 글은 완전히 분리

⸻

3. 파일명(slug) 규칙
	•	영문 소문자 kebab-case
	•	의미 중심
	•	날짜/한글/숫자 포함 금지
	•	slug는 영구 식별자 (변경하지 않음)

spring-boot-transaction.md
information-processing-engineer.md


⸻

4. 날짜(date) 운영
	•	과거 글 이주 시 실제 작성 날짜 지정 가능
	•	신규 글은 날짜 미지정 시 자동 생성
	•	날짜는 정렬/아카이빙 용도
	•	slug와 날짜는 완전히 분리

⸻

5. 제목·언어·SEO
	•	제목(title): 한국어 기본
	•	slug: 영문 고정
	•	tags: 한/영 혼합 허용
	•	문서당 하나의 주제만 다룸
	•	제목과 본문에 핵심 키워드 자연스럽게 포함

⸻

6. Front Matter (필수 최소)

---
title: "Spring Boot 트랜잭션 전파 방식 정리"
description: "Spring Boot 트랜잭션 전파 옵션과 실무 주의사항 정리"
category: "Spring"
tags: ["Spring Boot", "트랜잭션"]
draft: false
---


⸻

7. Markdown 작성 규칙

# 제목 (H1, 1개)
## 섹션 (H2)
### 하위 섹션 (H3)

	•	H1은 1개만 사용
	•	H2/H3로 논리적 구조 유지
	•	HTML 직접 작성 지양

⸻

8. 이미지 규칙
	•	이미지 파일은 static/images/ 아래에서만 관리
	•	글 slug 기준 폴더 사용

![설명](/images/posts/spring-boot-transaction/diagram.png)

	•	외부 이미지 링크 사용 지양

⸻

9. 디자인·유지보수 원칙
	•	PaperMod 기본 구조 최대 활용
	•	JS/CSS는 필요할 때만 추가
	•	특정 기술(JS 구조, 폴더)을 강제하지 않음
	•	커스터마이징보다 일관성과 유지보수성 우선
