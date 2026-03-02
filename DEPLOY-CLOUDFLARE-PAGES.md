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

## 권장 추가 작업

- `contact.html` 폼을 실제 수신 서비스(Formspree/Workers API)와 연동
- `portfolio.html` 샘플 데이터를 실제 와이너리/SKU 데이터로 교체
- Google Search Console / 네이버 서치어드바이저 등록
