# **Github flavored Markdown-extension part**

<br>

#### 읽기 전에)

- 각 문법마다 사용 예시를 넣어놨으니까 실제 어떻게 표현되는지는 복붙해서 확인해볼 것
- 아래 <간략히 살표보기> 표의 element들을 누르면 해당 문법이 있는 부분으로 이동됨

<br>

## **간략히 살펴보기**

 |No.|element|GFM|
 |:---:|:---:|:---:|
 |1| Table |  |
 |2| Task list item |  |
 |3| Strikethrough |  |
 |4| Autolink |  |
 |5| Disallowed Raw HTML |  |

<br><br><br>

## ***1. Table***

- **table(표)**를 만들 때 사용
- table은 header row(제목이 들어가있는 행), delimiter row(heading과 데이터를 구분해주는 행), data rows(데이터가 들어있는 행, 0~)으로 이루어진 행과 열의 배열
- 각각의 행들은 |로 구분지어지는 셀들로 이루어짐
- 구문 분석의 명확성을 위해 셀 앞뒤로 |를 붙이는 것을 권장
- 셀의 내용과 | 사이의 띄어쓰기는 무시되며, block level의 요소는 셀에 들어가지 못함
