# comentocv
# CV Project - OpenCV Red Color Detection

프로젝트 소개
본 프로젝트는 OpenCV와 NumPy를 활용하여 이미지에서 빨간색 영역을 검출하는 프로그램을 구현한 프로젝트이다.  
Git과 GitHub를 활용하여 브랜치 생성, 커밋, Push, Pull Request(PR), Merge 과정까지 함께 진행하였다.

---

# 개발 환경
Language  Python
Library OpenCV, NumPy
Tool VS Code
Version Control Git, GitHub


# Git 작업 과정

# 1. Git 저장소 초기화
```bash
git init
```

로컬 프로젝트 디렉토리를 Git 저장소로 초기화하였다.

---

# 2. 원격 저장소 복제
```bash
git clone <repository_url>
```

GitHub 저장소를 로컬 환경으로 복제하였다.

---

# 3. 브랜치 생성
```bash
git branch ijin
```

기능 개발을 위한 작업 브랜치를 생성하였다.

---

# 4. 브랜치 이동
```bash
git checkout ijin
```

`ijin` 브랜치로 이동하여 개발을 진행하였다.

---

# 이미지 처리 기능 구현

# 주요 기능
- 이미지 파일 불러오기
- HSV 색상 공간 변환
- 빨간색 범위 지정
- 마스크 생성
- 빨간색 영역만 추출
- 결과 이미지 출력

---

# 구현 코드

```python
import cv2
import numpy as np

# 이미지 로드
image = cv2.imread('sample.jpg')

# HSV 색상 공간 변환
hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)

# 빨간색 범위 지정
lower_red1 = np.array([0, 120, 70])
upper_red1 = np.array([10, 255, 255])

lower_red2 = np.array([170, 120, 70])
upper_red2 = np.array([180, 255, 255])

# 마스크 생성
mask1 = cv2.inRange(hsv, lower_red1, upper_red1)
mask2 = cv2.inRange(hsv, lower_red2, upper_red2)

# 마스크 결합
mask = mask1 + mask2

# 빨간색 영역 추출
result = cv2.bitwise_and(image, image, mask=mask)

# 결과 출력
cv2.imshow('Original', image)
cv2.imshow('Red Filtered', result)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

# Git 변경사항 관리

# 상태 확인
```bash
git status
```

현재 변경된 파일 상태를 확인하였다.

---

# 파일 스테이징
```bash
git add .
```

전체 변경 파일을 스테이징 영역에 추가하였다.

---

# 커밋 생성
```bash
git commit -m "Add red color detection feature"
```

빨간색 검출 기능 구현 내용을 커밋하였다.

---

# GitHub 업로드

# 브랜치 Push
```bash
git push origin ijin
```

작업 브랜치를 GitHub 원격 저장소에 업로드하였다.

---

# Pull Request(PR)

# PR 생성 과정
1. GitHub 저장소 접속
2. `Compare & pull request` 클릭
3. `base: main` / `compare: ijin` 설정
4. PR 제목 및 설명 작성
5. `Create Pull Request` 클릭

---

# Merge 과정

## PR 병합
GitHub에서 `Merge Pull Request`를 수행하여  
`ijin` 브랜치의 내용을 `main` 브랜치에 병합하였다.

---

# 프로젝트 결과

- OpenCV 기반 색상 검출 기능 구현
- HSV 색상 공간 이해
- 이미지 마스킹 처리 학습
- Git 브랜치 전략 실습
- GitHub 협업 프로세스(PR & Merge) 경험

---
