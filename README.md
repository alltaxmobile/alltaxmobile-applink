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

- `8GL8NVSJD3.kr.co.alltaxmobile.ios`

### 3. 스토어 URL

아래 값이 실제 운영 링크와 맞는지 확인하세요.

- App Store: `https://apps.apple.com/kr/app/%EC%98%AC%ED%83%9D%EC%8A%A4-%EB%82%B4%EC%86%90%EC%95%88%EC%9D%98-%EC%84%B8%EB%AC%B4-%EB%B9%84%EC%84%9C/id6529523756`
- Play Store: `https://play.google.com/store/apps/details?id=kr.co.alltaxmobile.aos`

## 앱 화면 이동 링크

앱에서는 아래 링크를 처리합니다.

- 멤버십: `https://app.alltaxmobile.co.kr/membership`
- 채널톡: `https://app.alltaxmobile.co.kr/channeltalk`
- 웹페이지: `https://app.alltaxmobile.co.kr/web?url={percent-encoded URL}`
- 결제수단 관리: `https://app.alltaxmobile.co.kr/payment_method_manage`
- 지원사업 상세: `https://app.alltaxmobile.co.kr/employedcenter_feed_detail?id={id}`

`/open` fallback 페이지를 사용하는 경우에도 같은 화면을 열 수 있습니다.

- `https://app.alltaxmobile.co.kr/open?screen=membership`
- `https://app.alltaxmobile.co.kr/open?screen=channeltalk`
- `https://app.alltaxmobile.co.kr/open?screen=web&url={percent-encoded URL}`
- `https://app.alltaxmobile.co.kr/open?screen=payment_method_manage`
- `https://app.alltaxmobile.co.kr/open?screen=employedcenter_feed_detail&id={id}`

웹페이지 링크 예시:

```text
https://app.alltaxmobile.co.kr/web?url=https%3A%2F%2Fexample.com%2Fnotice%3Fid%3D123%26type%3Dtax
```

로그인하지 않은 사용자의 링크는 로그인 완료 후 처리하며, 결제수단 관리는
사업장 연결이 되어 있어야 진입합니다.
