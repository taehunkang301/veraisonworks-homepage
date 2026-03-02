# Cloudflare Pages 배포 가이드 (Verasion Works)

이 문서는 현재 프로젝트(`/Users/taehunkang/veraison/homepage`)를 기준으로 작성되었습니다.

## 1) GitHub에 코드 올리기

```bash
cd /Users/taehunkang/veraison/homepage
git init
git add .
git commit -m "Initial website for Verasion Works"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
```

`<YOUR_GITHUB_REPO_URL>` 예시:
- `https://github.com/<username>/verasion-works-site.git`

## 2) Cloudflare에 도메인 추가

1. Cloudflare Dashboard -> Websites -> Add a domain
2. 도메인 입력 후 Free 플랜 선택
3. Cloudflare가 제공한 네임서버 2개를 확인
4. 도메인 구매처에서 기존 네임서버를 Cloudflare 네임서버로 변경
5. Cloudflare 상태가 `Active`가 될 때까지 대기

## 3) Pages 프로젝트 생성 (Git 연동)

1. Cloudflare Dashboard -> Workers & Pages -> Create application -> Pages
2. `Connect to Git` 선택
3. GitHub 연동 후 저장소 선택
4. 빌드 설정 입력
   - Framework preset: `None`
   - Build command: 비움
   - Build output directory: `/`
5. `Save and Deploy` 클릭

## 4) 커스텀 도메인 연결

1. Pages 프로젝트 -> Custom domains -> Set up a domain
2. `verasionworks.com` 또는 `www.verasionworks.com` 입력
3. DNS 레코드 자동 생성 여부 확인
4. HTTPS 활성화 완료 확인

## 5) 운영

- 수정 -> `main` 브랜치 push -> Cloudflare Pages 자동 재배포
- 문제 발생 시: Pages -> Deployments -> 실패 배포 로그 확인

## 6) 문의 폼(FormSubmit) 확인

현재 `contact.html`은 아래 설정으로 실제 메일 전송됩니다.

- 전송 주소: `contact@verasionworks.com`
- 폼 액션: `https://formsubmit.co/contact@verasionworks.com`
- 완료 페이지: `https://verasionworks.com/thanks.html`

운영 전 체크:

1. 첫 테스트 제출 후 수신된 FormSubmit 승인 메일에서 폼을 활성화
2. `verasionworks.com` 연결 전 테스트 시 `_next` 주소를 임시 도메인으로 변경 필요

## 권장 추가 작업

- Google Search Console / 네이버 서치어드바이저 등록
