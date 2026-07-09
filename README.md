# 고스트 마네킹 변환 페이지

SSAKA STUDIO 평면컷 → 고스트마네킹 PNG 변환용 GitHub Pages 프로젝트입니다.

## 운영 방식

- GitHub 저장소에는 HTML/CSS/JS 파일만 업로드합니다.
- Gemini API Key는 코드에 넣지 않습니다.
- 사용자가 페이지 접속 후 브라우저에서 API Key를 직접 입력합니다.
- 입력된 API Key는 해당 브라우저의 `localStorage`에만 저장됩니다.
- 이미지 생성 요청 시 브라우저에서 Gemini API로 직접 호출합니다.

## API Key 보안 원칙

`index.html` 안에는 실제 API Key를 절대 넣지 않습니다.

```js
const DEFAULT_API_KEY = '';
```

위 값은 반드시 빈 문자열로 유지해야 합니다. 실제 Key를 넣고 public GitHub에 push하면 Google secret scanner가 감지해 키가 자동 차단될 수 있습니다.

## 배포

GitHub Pages에서 `main` 브랜치의 루트 경로를 배포 소스로 사용하면 됩니다.

접속 후 첫 화면에서 Gemini API Key를 입력하고 저장하면 변환 기능을 사용할 수 있습니다.
