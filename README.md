# NA2study — 네트워크관리사 2급 학습 관리실

`260122-crypto/NA2study` 저장소에 올릴 수 있는 GitHub Pages용 독립 실행형 프로토타입입니다.

## 포함 기능
- **이론**: 주제별 학습 체크리스트와 진도율
- **필기**: 선택형 문제, 자동 채점, 해설, 오답노트, 북마크
- **실기**: 작업형·실습형·단답형/객관식 분류, 체크리스트와 개인 메모
- **학습 분석**: 영역별 정답률, 최근 점수 추이, 주제별 취약점, 오답 해결률, 시도 이력
- **로컬 기록**: 브라우저 `localStorage` 자동 저장, JSON 백업 및 복원
- **문제은행 관리**: 문항 추가 및 JSON 가져오기

## 로컬 실행
`index.html`을 Chrome 또는 Edge에서 엽니다. 로컬 파일 정책이 저장을 제한하는 환경에서는 아래처럼 간단한 개발 서버를 사용하세요.

```bash
python -m http.server 8000
```

그 다음 `http://localhost:8000`을 엽니다.

## GitHub Pages 배포
1. 이 패키지의 `index.html`, `README.md`, `.nojekyll`, `.github/workflows/pages.yml`을 `260122-crypto/NA2study` 저장소 루트에 업로드합니다.
2. 저장소의 **Settings → Pages → Build and deployment → Source**에서 **GitHub Actions**를 선택합니다.
3. `main` 브랜치에 커밋하면 `Deploy to GitHub Pages` 워크플로가 사이트를 배포합니다.

## 데이터·콘텐츠 범위
- 모든 학습 기록은 사용 중인 브라우저 프로필의 `localStorage`에 보관됩니다. 다른 브라우저/기기와 자동 동기화되지 않으므로 JSON 백업을 권장합니다.
- 기본 문항은 기능을 확인하기 위한 예시 문항입니다. 원본 `sumilee-phd/NA2-study`의 전체 필기 900문항, 원본 이론 자료, 실기 검수 문항을 이 패키지에 복제·연결한 상태는 아닙니다.
- 원본 저장소 README에서 확인되는 구조는 이론 학습센터, 필기 900문항, 실기 작업형/실습형/단답형·객관식, 케이블링, 학습 기록입니다. 원본 앱의 데이터 형식과 기록 키를 보존한 통합을 하려면 원본 소스 파일을 대상 프로젝트에 가져와 별도로 병합해야 합니다.
- 이 도구는 학습용이며 공식 시험 감독·실물 장비 실행·실물 케이블 성능 측정 기능은 제공하지 않습니다.

## 권장 다음 통합 단계
1. 원본의 `src/`, `public/`, `content-review/`, `tests/`, `package.json`을 대상 저장소로 가져옵니다.
2. 기존 기록 키(`na2_study_learning_v1`, `na2_study_written_v1`, `na2_study_cabling_v1`, `na2_study_practical_v1`, `na2_study_labs_v1`)와 호환되는지 테스트합니다.
3. 이 패키지의 분석 기능을 원본 React 화면과 저장 모듈에 통합하고, 기존 기록 백업/복원 테스트를 실행합니다.
