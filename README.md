# Verasion Works Homepage

일본 와인 수입사 `베레종 웍스 (Verasion Works)`의 정적 홈페이지입니다.

## 프로젝트 구조

- `index.html`: 메인 페이지
- `about.html`: 회사 소개
- `portfolio.html`: 와이너리/와인 포트폴리오
- `contact.html`: B2B 문의
- `privacy.html`: 개인정보처리방침
- `assets/styles.css`: 공통 스타일

## 로컬 확인

정적 파일이므로 브라우저로 `index.html`을 열어 바로 확인할 수 있습니다.

## Cloudflare Pages 배포

1. GitHub 저장소 생성 후 현재 파일 업로드
2. Cloudflare Dashboard -> Workers & Pages -> Create application -> Pages -> Connect to Git
3. 해당 GitHub 저장소 연결
4. Build settings
   - Framework preset: `None`
   - Build command: 비워두기
   - Build output directory: `/`
5. Deploy 클릭
6. 배포 완료 후 `*.pages.dev` 주소에서 동작 확인

## 커스텀 도메인 연결

1. 도메인을 Cloudflare로 위임(네임서버 교체)
2. Pages 프로젝트 -> Custom domains -> Set up a domain
3. 대표 도메인 지정 (`www` 또는 루트)
4. HTTPS 인증서 발급 완료 확인

## 운영

`main` 브랜치에 푸시할 때마다 Cloudflare Pages가 자동 배포합니다.
