# 기타 쓸모 있을 것 같은 것들

### MS Excel ↔ colab, pandas 사이의 csv 파일 교환

```python
#load csv file from MS Excel on Windows
data_frame=pd.load_csv('csv_file.csv', encoding='euc-kr')
#save csv file to open with MS Excel on Windows
data_frame.to_csv('csv_file.csv', encoding='euc-kr')
```

pandas dataframe으로 여는 경우 

## 디버깅, 매직메소드

- pdb는 뭐고 debug는 뭔가?
    
    [Built-in magic commands — IPython 8.6.0 documentation](https://ipython.readthedocs.io/en/stable/interactive/magics.html)
    
    [[python] jupyter notebook 에서 디버깅 (debug) 하기 #ipdb 명령어 (tistory.com)](https://stricky.tistory.com/93)
    
    | 명령어 | 설명 |
    | --- | --- |
    | help | debug help |
    | w | where (stack trace) |
    | s | next step |
    | n | next line |
    | r | continue to return |
    | b | set break on specific line |
    | c | continue to break |
    | a | argument of current func |
    | p | print value |
    | cl | clear break point |
    | q | quit |
    | d | go to down stack frame |
    | u | go to upside stack frame |

## 주피터 노트북으로 프리젠테이션? ←어케 하는거지

[https://medium.com/@mjspeck/presenting-code-using-jupyter-notebook-slides-a8a3c3b59d67](https://medium.com/@mjspeck/presenting-code-using-jupyter-notebook-slides-a8a3c3b59d67)

→ local말고 LMS등에서는 안되나?: 일단 저걸 실행하면 html파일이 생긴다. slide는 화살표를 넘기면 나오고, sub-slide는 소속 slide에서 밑으로 화살표를 누르면 표시된다. **두 셀을 같이 표시하려면 Fragment**

`jupyter nbconvert Slides.ipynb --to slides --post serve`

## Weight and Bias 사용법

11일 있었던 튜토리얼에서 간단한 설명을 추가.

[https://drive.google.com/file/d/1LzDkVt2_JuHEyXxRttwEFXBQKxRvIf9e/view?usp=share_link](https://drive.google.com/file/d/1LzDkVt2_JuHEyXxRttwEFXBQKxRvIf9e/view?usp=share_link)

## WSL 에서 주피터 노트북 실행

그런데 이것은 WSL2가 나오기 전에 작성된 것 같다. ubuntu20.04에 익숙해지려면 그냥 이걸 쓰는 것도 좋을 거 같다.

[WSL에서의 Jupyter notebook 사용하기. :: Orca's Develop Blog (tistory.com)](https://ksjm0720.tistory.com/14)

## 기상자료개방포털 FTP 연결 주의할 점

passive 모드로 해야 할 것입니다… 포트 개방도 해야 할 것임
