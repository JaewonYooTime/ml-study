# Titanic ML – Kaggle 베이스라인 따라잡기

타이타닉 생존자 예측 문제를 **5 분 안에 재현**할 수 있도록 정리한 프로젝트입니다.
데이터 탐색 → 전처리 → 여러 모델 학습 → Kaggle 제출까지 한 번에 경험합니다.

---

## 🚀 빠른 시작

```bash
# 저장소 클론
git clone https://github.com/<YOUR_ID>/titanic-ml.git
cd titanic-ml

# (선택) 가상환경 생성
pip install -r requirements.txt

# 주피터 실행 & 노트북 전체 실행
jupyter lab               # notebooks/titanic_eda.ipynb → Run All
```

1. `notebooks/titanic_eda.ipynb` 전체 실행
2. `submission_<모델>.csv` 자동 생성
3. Kaggle Titanic 대회에 업로드

---

## 📂 폴더 구조

```
titanic-ml/
├─ data/                # 원본 CSV
│  ├─ train.csv
│  ├─ test.csv
│  └─ gender_submission.csv
├─ notebooks/           # 분석 노트북 & 제출 파일
│  ├─ titanic_eda.ipynb
│  ├─ submission.csv            # Logistic
│  ├─ submission_fs.csv         # +FamilySize/IsAlone
│  ├─ submission_gb.csv         # GradientBoosting
│  ├─ submission_rf.csv         # RandomForest
│  └─ submission_xgb.csv        # XGBoost
├─ src/                # (예정) 스크립트 · API 코드
└─ README.md
```

> `.ipynb_checkpoints/`, `.DS_Store` 등은 **.gitignore** 로 제외됩니다.

---

## ✨ 파생 변수

| 변수           | 정의                  | 통찰               |
| ------------ | ------------------- | ---------------- |
| `FamilySize` | `SibSp + Parch + 1` | 일행 규모가 클수록 생존률 ↑ |
| `IsAlone`    | `FamilySize == 1`   | 혼자 탑승 시 생존률 ↓    |

---

## 🏆 모델 비교 (검증 vs Kaggle)

| 모델                                     | 검증 정확도 | Kaggle 점수 |
| -------------------------------------- | -----: | --------: |
| Logistic + 파생                          |  0.810 | *(제출 예정)* |
| Gradient Boosting (400, 0.03, depth 2) |  0.832 | *(제출 예정)* |
| Random Forest (depth 5)                |  0.820 | *(제출 예정)* |
| XGBoost (튜닝)                           |  0.782 | *(제출 예정)* |

*Kaggle 점수는 다음 제출 후 갱신 예정입니다.*

---

## 🔜 로드맵

* [ ] `src/` 모듈화 (`train.py`, `predict.py`)
* [ ] FastAPI + Docker 배포 `/predict`
* [ ] MLflow 실험 관리 & CI 파이프라인

---

## 📜 라이선스

MIT
