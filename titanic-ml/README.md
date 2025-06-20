```markdown
# Titanic ML (0.81 Baseline)

머신러닝 입문용 프로젝트로 **타이타닉 생존자 예측**을 다룹니다.  
데이터 탐색 → 전처리 → 로지스틱 회귀 모델 학습 → Kaggle 제출까지의 가장 짧은 흐름을 담고 있습니다.

---

## 📂 프로젝트 구조

```
titanic-ml/
├─ .DS_Store
├─ .ipynb_checkpoints/
├─ README.md
├─ data/
│   ├─ gender_submission.csv
│   ├─ test.csv
│   └─ train.csv
└─ notebooks/
    ├─ .ipynb_checkpoints/
    │   └─ titanic_eda-checkpoint.ipynb
    ├─ submission.csv
    └─ titanic_eda.ipynb

````

---

## ⚙️ 요구 사항

- Python ≥ 3.9  
- 주요 패키지: `pandas numpy scikit-learn seaborn matplotlib`  

---

## 🚀 실행 순서 (3-Step)

1. **Jupyter**에서 `notebooks/titanic_eda.ipynb` 열기
2. 메뉴 → **Run All** (모든 셀 실행)
3. 생성된 `notebooks/submission.csv`를 Kaggle Titanic 대회에 업로드

> 기본 전처리 + 로지스틱 회귀로 Kaggle 리더보드 약 **0.76** 점수를 얻습니다.

---

## ✨ 다음 개선 아이디어

* `FamilySize`, `IsAlone` 등 파생 변수 추가해 점수 +0.01 \~ 0.03 ↑
* `RandomForestClassifier`, `GradientBoosting` 모델 비교
* FastAPI + Docker로 `/predict` 엔드포인트 배포

```

> 위 템플릿에서 **트리 구조** 영역만 최신 디렉터리 상태에 맞춰 갱신해 붙여 넣으면 바로 사용­가능합니다.
```
