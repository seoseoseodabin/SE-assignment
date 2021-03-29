# **Github flavored Markdown-extension part**

## ***1. Table***

- **table**(표)를 만들 때 사용
- table은 **header row**(헤더가 들어있는 행), **delimiter row**(header와 데이터를 구분해주는 행), **data rows**(데이터가 들어있는 행, 0~)으로 이루어진 행과 열의 배열
- 각각의 행들은 **|(pipe)로 구분지어지는 셀**들로 이루어짐
- 구문 분석의 명확성을 위해 **셀 앞뒤로 |를 붙이는** 것을 권장
- **셀의 내용과 | 사이의 띄어쓰기는 무시**되며, **block level의 요소는 셀에 들어가지 못함**

<br>

- **delimiter row는 -(hyphen)으로만 구성**되며, **:(colon)을 이용해 왼쪽, 오른쪽, 가운데 정렬**을 나타낼 수 있음
- 한 열에 있는 **셀들의 길이는 일치할 필요 없음**
- **앞 뒤로 붙이는 |도 일관될 필요 없음**
    
      | header1  | header2  |
      | -------- | -------- |
      | content1 | content2 |
      
      | abc | defghi |
      :-: | -----------:
      bar | baz

- **셀 안에서 |를** 표현할 땐, **앞에 \를** 붙임

      | one \| header |
      | ------ |
      | one `\|` column |
      | one **\|** cell |
