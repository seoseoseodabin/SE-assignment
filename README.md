# **Github flavored Markdown-extension part**

#### 읽기 전에)

- 각 문법마다 사용 예시를 넣어놨으니까 실제 어떻게 표현되는지는 복붙해서 확인해볼 것
- 아래 표 안의 index를 누르면 해당 extension이 있는 부분으로 이동함

<br>

|no.|index|
|:-:|:---:|
|1|[Table(extension)](#1-table)|
|2|[Task list item(extension)](#2-task-list-item)|
|3|[StrikeThrough(extension)](#3-strikethrough)|
|4|[Autolink(extension)](#4-autolink)|
|5|[Disabled Raw HTML(extension)](#5-disable-raw-html)|

<br><br>

## ***1. Table***

- **table**(표)를 만들 때 사용
- table은 **header row**(헤더가 들어있는 행), **delimiter row**(header와 데이터를 구분해주는 행), **data rows**(데이터가 들어있는 행, 0~)으로 이루어진 행과 열의 배열
- 각각의 행들은 **|(pipe)로 구분지어지는 셀**들로 이루어짐
- 구문 분석의 명확성을 위해 **셀 앞뒤로 |를 붙이는** 것을 권장
- **셀의 내용과 | 사이의 띄어쓰기는 무시**되며, **block level의 요소는 셀에 들어가지 못함**
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

- table은 **첫 번째 빈줄**과 **블록 레벨의 구조 시작**에서 **끝남**
- 첫번째 예시에서 bar1과 bar2는 table에 포함되지만 bar3은 첫 번째 빈줄 뒤에 나오기 때문에 포함 안 됨

      | abc  | def |
      | ---_ | --- |
      | bar1 | baz |
      bar2
      
      bar3

      | header1  | header2  |
      | :------: | :------: |
      | content1 | content2 |
      > beginning of another block-level structure

- table로 인식되기 위해서는 **header row의 셀 개수**와 **delimiter row의 셀 개수**가 **일치**해야 됨

      | one | two |
      | --- |
      | bar |

- **header row의 셀 개수에 비해 data row의 셀 개수가 적으면 빈칸**으로 표시되고, **많으면 그 셀은 무시**됨

      | abc | def |
      | --- | --- |
      | bar |
      | bar | baz | boo |

- **table body에 행이 없으면 없는 채로** 표가 만들어짐 (HTML로 따지자면 **`<tbody>`가 안 만들어진 것**과 같음)

      | abc | def |
      | --- | --- |

<br><br>

## ***2. Task list item***

- list에 추가적인 작업을 통해 **Task list**를 만들 수 있음
- **task list item**은 **task list item marker와 최소 한 칸 이상의 빈 칸으로 구성된 list item**
- task list item marker은 **빈 칸**과 **[ ]**, 그리고 **대괄호 사이에 들어가는 문자(빈칸 혹은 알파벳 x)으로 구성**됨 (x는 대소문자 상관 없음)
- task list item은 HTML의 `<input type="checkbox">`처럼 렌더링 됨
- 대괄호 사이의 문자는 **빈 칸**일 때 **체크 해제**, **x**일 때 **체크된 상태**를 의미
- 체크박스는 최종적으로 **렌더링 된 상태에서 checking, unchecking** 하는 것이 **불가능**함 (동적인 상호작용 불가능)

      - [ ] item 1
      - [x] item 2

- 체크박스를 **중첩**시키는 것도 가능

      - [x] item 1
         - [ ] item 1.1
         - [x] item 1.2
      - [ ] item 2

<br><br>

## ***3. Strikethrough***

- **Strikethrough**를 적용하면 **글자에 줄이 그어짐** (가로줄이 글자를 통과해서 그어짐)
- **~~를 텍스트 앞뒤로 적어** 감싸면 됨

      ~~Hi~~ Hello, world!

- 다른 emphasis 구문과 마찬가지로, **strikethrough가 적용된 텍스트 사이**에 **새로운 단락이 들어서면 적용이 안 됨**

      This ~~has a
  
      new paragraph~~.

<br><br>

## ***4. Autolink***

- GFM에는 **자동적으로 링크가 만들어지는 Autolink extension**이 지원됨
- URL을 < >로 감싸지 않아도 링크를 만들 수 있음
- autolink는 **줄의 시작점, 공백 뒤, 혹은 \*, _, ~, (와 같은 delimiting 문자에 올** 수 있음

<br>

## extended www autolink

- extended www autolink는 **www 뒤에 오는 것이 유효한 도메인(valid domain)일 경우** 인식됨
- 유효한 도메인은 **영숫자, _, -로** 이루어졌으면서 **\.으로 나눠진 부분들로 구성**됨
- **무조건 .이 하나 이상** 포함되어 있어야 하고, **마지막 두 부분에 _가 포함되어 있으면 안 됨**
- scheme `http://`는 **자동으로 삽입**됨

      www.commonmark.org

- 유효한 도메인 뒤에는 **extended autolink path validation**을 적용함

- ## extended autolink path validation

    - 유효한 도메인 뒤에는, **'공백과 <이 아닌 문자'가 0개 이상 올 수도 있음**

          Visit www.commonmark.org/help for more information.

    - autolink 내부에 **후행 구두점**(?, !, ., ,, :, *, _, ~)이 포함될 순 있지만, **autolink의 일부로 간주되지는 않음**

          Visit www.commonmark.org.

          Visit www.commonmark.org/a.b.

    - autolink가 **)로 끝나면 괄호의 총 개수를 검사**함. **여는 괄호보다 닫는 괄호가 더 많으면 마지막 )를 autolink의 일부로 간주하지 않음**
    - 이는 괄호 안에 autolink를 포함하기 쉽도록 하기 위함임

          www.google.com/search?q=Markup+(business)
  
          www.google.com/search?q=Markup+(business)))
  
          (www.google.com/search?q=Markup+(business))
  
          (www.google.com/search?q=Markup+(business)

    - 위 사항은 링크가 )로 끝나는 경우에만 해당하고, **괄호가 링크 내부에만 있으면 상관하지 않음**

          www.google.com/search?q=(business))+ok

    - **autolink가 ;으로 끝나면 entity reference와 유사한지 검사**함. 앞의 텍스트가 &로 시작하고 뒤가 하나 이상의 영숫자이면 autolink에서 제외

          www.google.com/search?q=commonmark&hl=en

          www.google.com/search?q=commonmark&hl;

    - **<가 나오면 즉시 링크를 마침**

          www.commonmark.org/he<lp

<br>

## extended URL autolink

- extended URL autolink는 `http://`나 `https://` 뒤에 **유효한 도메인**, 그 뒤에 **0개 이상의 공백과 <가 아닌 문자**가 **extended autolink path validation에 따라 올 때** 인식됨

      http://commonmark.org

      (Visit https://encrypted.google.com/search?q=Markup+(business))

<br>

## extended email autolink

- extended email autolink는 **한 개 이상의 영숫자나 -, _, +가 .으로 분리**되어 포함되어 있고, **@ 심볼**이 있을 때 인식됨
- **.은 최소 하나** 있어야 하며, **마지막 문자가 -이거나 _이면 안 됨**
- scheme `mailto:`은 이메일 링크가 생성되면 **자동으로 삽입**됨

      foo@bar.baz

- **+는** **@의** 뒤에는 못 오고 **앞에만** 올 수 있음

      hello@mail+xyz.example isn't valid, but hello+xyz@mail.example is.

- **.과 -, _은 @의 양쪽에** 위치할 수 있음
- **오직 .만 메일의 끝**에 올 수 있는데, 이 경우에 .은 이메일 **주소의 일부로 간주되지 않음**

      a.b-c_d@a.b

      a.b-c_d@a.b.
  
      a.b-c_d@a.b-

      a.b-c_d@a.b_

<br><br>

## ***5. Disallowed Raw HTML***

- GFM에서 **HTML**을 사용할 때 **다음 태그들은 필터링**됨
    - `<title>`
    - `<textarea>`
    - `<style>`
    - `<xmp>`
    - `<iframe>`
    - `<noembed>`
    - `<noframes>`
    - `<script>`
    - `<plaintext>`
- 필터링은 앞에 오는 <을 entity `&lt`로 대체하며 수행됨
