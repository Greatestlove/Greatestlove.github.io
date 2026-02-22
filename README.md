# 🌿 포커스 가든 — 디지털 도파민 디톡스 타이머

집중력 강화 PWA 타이머. 탭을 이탈하면 키우던 식물이 시들어요.

## 🚀 배포 방법

### 1. Vercel (권장, 무료)
```bash
npx vercel --prod
```

### 2. Netlify (드래그 앤 드롭)
netlify.com → "Sites" → 폴더 드래그앤드롭

### 3. GitHub Pages
```bash
git init
git add .
git commit -m "init"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/focus-garden.git
git push -u origin main
# Settings → Pages → Source: main branch
```

## ✅ PWA 아이콘 설정

manifest.json이 PNG 아이콘을 참조하므로 배포 전 아이콘 변환이 필요합니다.

**옵션 A**: `icons/icon.svg`를 온라인 변환기로 PNG 변환
- https://svgtopng.com 에서 192×192, 512×512 두 가지 크기로 저장
- `icons/icon-192.png`, `icons/icon-512.png` 로 저장

**옵션 B**: manifest.json에서 SVG 직접 참조 (일부 브라우저 제한)
```json
"icons": [{"src": "icons/icon.svg", "sizes": "any", "type": "image/svg+xml"}]
```

## 📦 파일 구조
```
/
├── index.html      # 메인 앱
├── manifest.json   # PWA 설정
├── sw.js           # Service Worker (오프라인 지원)
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## 🔧 핵심 기능

| 기능 | API |
|------|-----|
| 탭 이탈 감지 | Page Visibility API |
| 경고음 / 완료음 | Web Audio API |
| 배경 소음 (백색/갈색/빗소리/숲) | Web Audio API BufferSource |
| 식물 시각 피드백 | SVG + CSS Animation |
| 통계 저장 | localStorage |
| 앱처럼 설치 | PWA (Service Worker + Manifest) |
| 오프라인 지원 | Service Worker Cache |
