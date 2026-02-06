<div align="center">

# VOID

**3D Interactive AI Chat Interface**

WebGL 파티클 구체 시각화와 글래스모피즘 UI를 결합한 AI 챗 인터페이스

<br/>

![React](https://img.shields.io/badge/React-19.2-61DAFB?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?logo=typescript&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-0.182-000000?logo=threedotjs&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.2-646CFF?logo=vite&logoColor=white)
![styled-components](https://img.shields.io/badge/styled--components-6.3-DB7093?logo=styledcomponents&logoColor=white)

</div>

---

## Tech Stack

| Category | Technology |
|:---|:---|
| **Framework** | React 19, TypeScript 5.9 |
| **Bundler** | Vite (Rolldown) |
| **3D Rendering** | Three.js, @react-three/fiber, @react-three/drei |
| **Styling** | styled-components |
| **Animation** | Framer Motion |
| **HTTP Client** | Axios |
| **Icons** | Lucide React |
| **Linting** | ESLint, typescript-eslint |

---

## Project Structure

```
void/
├── public/                   # Static assets
│   └── vite.svg
│
├── src/
│   ├── @types/               # TypeScript type definitions
│   │   └── api.ts            # API request/response interfaces
│   │
│   ├── assets/               # Images & icons
│   │   ├── logo.ico
│   │   └── react.svg
│   │
│   ├── components/           # Reusable UI components
│   │   ├── ChatInput.tsx     # Glassmorphism chat input
│   │   ├── GlassCard.tsx     # Keyword ranking card (glass UI)
│   │   ├── ParticleSphere.tsx# 3D particle sphere (custom shader)
│   │   ├── ResponseBox.tsx   # AI response display box
│   │   └── SendButton.tsx    # Send button (glass UI)
│   │
│   ├── pages/                # Page-level components
│   │   └── MainPage.tsx      # Main layout & state management
│   │
│   ├── services/             # API layer
│   │   └── userService.ts    # Axios instance & API calls
│   │
│   ├── styles/               # Global styles
│   │   └── GlobalStyles.ts   # styled-components global reset
│   │
│   ├── App.tsx               # Root component
│   └── main.tsx              # Entry point
│
├── index.html                # HTML template
├── vite.config.ts            # Vite configuration
├── tsconfig.json             # TypeScript config (base)
├── tsconfig.app.json         # TypeScript config (app)
├── tsconfig.node.json        # TypeScript config (node)
├── eslint.config.js          # ESLint configuration
└── package.json
```

---

## Features

### 3D Particle Sphere
- 커스텀 GLSL ShaderMaterial 기반 파티클 시스템
- Fibonacci sphere 분포를 활용한 균일한 파티클 배치
- 3D hash noise를 이용한 반경 변위 및 shimmer 효과
- 대각선 회전 + 파동 모션 애니메이션
- GPU 최적화 (프레임당 `uTime` uniform만 갱신)

### Glassmorphism UI
- `backdrop-filter: blur()` 기반의 유리 질감 컴포넌트
- 빛 반사 효과 (`::after`, `inset box-shadow`)
- Framer Motion 기반 등장/퇴장/호버 애니메이션

### API Integration
- `POST /ask` — AI 질의응답
- `GET /ranking/top3` — 실시간 인기 키워드 (20분 폴링)

---

## Getting Started

```bash
# Install dependencies
yarn install

# Set environment variables
cp .env.example .env
# Edit .env and set VITE_API_URL

# Start dev server
yarn dev

# Build for production
yarn build

# Preview production build
yarn preview
```

### Environment Variables

| Variable | Description |
|:---|:---|
| `VITE_API_URL` | Backend API base URL |

---

<div align="center">

**VOID** &copy; oneWave

</div>
