# 한국어 NLP와 워드 클라우드 시각화

이 프로젝트는 Python을 활용한 한국어 자연어 처리(NLP) 기법을 Konlpy, NLTK, WordCloud와 같은 라이브러리를 통해 구현합니다. 텍스트 토큰화, 형태소 분석, 단어 빈도 시각화 등을 다루며, 사용자 정의 마스크를 활용한 워드 클라우드를 생성합니다. 또한, Matplotlib에서 한국어 폰트가 올바르게 표시되도록 운영 체제별 폰트 설정을 포함합니다.

# 프로젝트 예시
- 코로나 관련 기사에 있는 한 문장을 가져와 문장 및 형태소를 분석
- 오징어게임 관련 글에서 워드 클라우드를 생성
- 입법 문서를 토대로 각각의 단어의 빈도와 분포를 분석하고 시각화

# 주요 기능

- **문장 및 형태소 분석**: Konlpy의 Kkma, Hannanum, Okt를 이용한 문장 토큰화와 형태소 분석 기능을 사용합니다.
- **워드 클라우드 생성**: 불용어 제거, 빈도 필터링, 마스크를 적용한 사용자 정의 워드 클라우드를 생성합니다.
- **단어 빈도 분석**: NLTK를 활용하여 한국어 입법 문서에서 단어 빈도와 분포를 분석하고 시각화합니다.
- **운영 체제별 폰트 호환성**: macOS와 Windows에서 한글 폰트를 지원하며, Linux의 경우 한글 폰트가 설치되어 있어야 합니다.

# 설치 및 설정

1. **필요 라이브러리 설치**:
   ```bash
   pip install konlpy wordcloud numpy matplotlib nltk

2. **운영 체제별 폰트 설정**:

```python
from matplotlib import font_manager, rc
import platform

if platform.system() == 'Darwin':  # macOS
    rc('font', family='AppleGothic')
elif platform.system() == 'Windows':  # Windows
    path = 'c:/Windows/Fonts/malgun.ttf'
    font_name = font_manager.FontProperties(fname=path).get_name()
    rc('font', family=font_name)
else:
    print('Linux 또는 기타 시스템에서는 한글 폰트를 별도로 설정해야 합니다.')
```



- **macOS**: AppleGothic 폰트를 사용합니다.
- **Windows**: Windows 폴더의 malgun.ttf 폰트를 사용합니다.
- **Linux**: Linux는 이 프로젝트에서 중요하게 다루지 않기 때문에 안내 메세지만 띄우도록 합니다.

3. **데이터 및 마스크 이미지 준비**:

- 텍스트 데이터 파일과 마스크 이미지를 지정된 디렉토리에 배치합니다.
  
