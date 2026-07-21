# alltaxmobile-applink

올택스 앱 링크용 정적 웹 프로젝트입니다.

## 포함 내용

- 앱이 없을 때 스토어로 보내는 fallback 페이지
- Android App Links 검증 파일
- iOS Universal Links 검증 파일

## 배포 전 수정 필요

### 1. Android SHA-256

`/.well-known/assetlinks.json`의 아래 값을 실제 릴리즈 인증서 SHA-256으로 교체하세요.

- `REPLACE_WITH_RELEASE_SHA256`

### 2. iOS Team ID / Bundle ID

`/.well-known/apple-app-site-association`의 아래 값을 실제 값으로 교체하세요.

- `REPLACE_WITH_TEAM_ID.kr.co.alltaxmobile.ios`

### 3. 스토어 URL

아래 값이 실제 운영 링크와 맞는지 확인하세요.

- App Store: `https://apps.apple.com/kr/app/%EC%98%AC%ED%83%9D%EC%8A%A4-%EB%82%B4%EC%86%90%EC%95%88%EC%9D%98-%EC%84%B8%EB%AC%B4-%EB%B9%84%EC%84%9C/id6529523756`
- Play Store: `https://play.google.com/store/apps/details?id=kr.co.alltaxmobile.aos`
