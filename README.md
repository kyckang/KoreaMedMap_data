# 병원약국맵 공개 데이터

"병원약국맵(Korea Med Map)" 앱이 받아 쓰는 전국 약국·병의원 데이터입니다. 앱 저장소의 GitHub Actions가 매일 새로 만들어, 바뀐 것이 있을 때만 올립니다. 저장 공간을 아끼려고 **기록 없이 최신본 하나만** 둡니다. **이 저장소의 파일은 직접 고치지 마세요.** 다음 갱신 때 덮어씌워집니다.

| 파일 | 내용 |
|---|---|
| `v1/med.db.bin` | SQLite 데이터베이스(gzip 압축, 확장자만 .bin) — 약국·병의원(이름, 주소, 전화, 좌표, 요일별 진료시간, 진료과목, 응급실 운영 여부), 진료과목·기관 종별 코드표, 공휴일 |
| `v1/data_manifest.json` | 생성 시각, 건수, sha256(앞 16자리), 형식 버전 |
| `v1/diffs/<sha>.json.gz` | 그 sha 의 배포본 → 다음 배포본 변경분(바뀐 행만). 앱은 이걸 이어 받아 하루 몇 KB 만 받는다. 최근 60개 |
| `v1/diffs/index.json` | 변경분 목록 (from · to · 시각 · 크기) |

`v1` 은 형식 버전입니다. 표 구성이 바뀌면 `v2` 폴더를 새로 만들어, 옛 앱은 계속 `v1` 을 받게 합니다.

## 출처

- 국립중앙의료원 전국 약국·병의원 정보, 코드마스터 (공공데이터포털)
- 건강보험심사평가원 약국·병원 정보 (공공데이터포털) — 공공누리 제1유형, 폐업·휴업 교차검증용
- 한국천문연구원 특일 정보 (공공데이터포털) — 공휴일

진료시간은 각 기관이 신고한 값입니다. 실제와 다를 수 있으니 방문 전에 전화로 확인하세요.

This repository holds nationwide pharmacy and clinic data (names, locations, opening hours, specialties) built daily from Korean government open data (with small daily diffs) for the Korea Med Map app. Opening hours are as reported by each institution; please call ahead.
