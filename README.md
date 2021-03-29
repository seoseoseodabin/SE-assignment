# **Markdown Basic Syntax**

<br>

#### 읽기 전에)

- 각 문법마다 사용 예시를 넣어놨으니까 실제 어떻게 표현되는지는 복붙해서 확인해볼 것
- 아래 <간략히 살표보기> 표의 element들을 누르면 해당 문법이 있는 부분으로 이동됨

<br>

## **간략히 살펴보기**

 |No.|element|markdown|
 |:---:|:---:|:---:|
 |1| [Heading](#1.%20Heading) | \# heading |
 |2| [Paragraph](#2.%20Paragraph) | paragraph1<br><br>paragraph2 |
 |3| [Line Break](#3.%20Line%20Break) | first line \<br>second line |
 |4| [Emphasis](#4.%20Emphasis) | \*\*Bold text\*\*<br>\*Italic text\* |
 |5| [Blockquote](#5.%20Blockquote) | \> blockquote |
 |6| [List](#6.%20List) | 1. first item<br>2. second item |
 |7| [Code](#7.%20Code) | \`I am a code\` |
 |8| [Horizontal Rule](#8.%20Horizontal%20Rule) | *** |
 |9| [Link](#9.%20Link) | \[text](URL "title") |
 |10| [Image](#10.%20Image) | ![alt](image URL "title") |
 |11| [Escaping Character](#11.%20Escaping%20Character) | \\\* |

<br><br><br>

## ***1. Heading***

- **제목**을 나타낼 때 사용  
- **#의 개수**로 크기 조정. 적을수록 크기가 커지며, 레벨 1~6까지 있음  
- #과 제목 사이는 **한 칸 이상** 띄어있어야 함  

      # Heading level 1  
      ## Heading  level 2  
      ### Heading level 3  
      #### Hading level 4  
      ##### Heading level 5  
      ###### Heading level 6  

- **레벨 1과 2**는 **다음 줄에 각각 ==와 --를** 추가하는 방식으로도 사용 가능. 개수는 상관 없음  

      Heading level 1  
      ===============
      Heading level 2  
      ---------------

<br><br>

## ***2. Paragraph***

- **단락**을 나타낼 때 사용
- 단락과 단락 사이에 **빈 줄**을 넣음
- 단락이 리스트에 있지 않은 이상 스페이스나 탭으로 **들여쓰기 하면 안 됨**

      paragraph 1  
      
      paragraph 2  

<br><br>

## ***3. Line Break***

- **줄바꿈** 할 때 사용  
- **두 칸 이상** 띄어쓴 후 다음 줄로 넘어감  

      first line  
      second line

- **HTML의 \<br> 태그**도 대부분의 마크다운 어플리케이션에서 지원함

      first line<br>  
      second line

<br>
<br>

## ***4. Emphasis***

- ## *Bold*  

    - **굵은 글씨**로 강조할 때 사용  
    - 단어나 구의 **앞뒤에 \*\*이나 \_\_을** 붙임  
    - 단, **단어 사이**에 사용할 땐 **\*\*를** 사용하여야 함

        |markdown|rendered|
        |:---:|:---:|
        |\*\*Bold text\*\*|**Bold text**|
        |\_\_Bold text\_\_|__Bold text__|  
        |Thisis\*\*Bold\*\*text|Thisis**Bold**text|

<br>

- ## *Italic*

    - **이탤릭체**(글씨를 기울일 때)에 사용
    - 단어나 구의 **앞뒤에 \*이나 \_을** 붙임
    - 단, **단어 사이**에 사용할 땐 **\*를** 사용하여야 함

        |markdown|rendered|
        |:---:|:---:|
        |\*Italicized text\*|*Italicized text*|
        |\_Italicized text\_|_Italicized text_|
        |Thisis\*Italicized\*text|Thisis*Italicized*text|

<br>

- 두 개를 같이 사용할 땐 **안 쪽에 Italic 표시**가, **바깥 쪽에 Bold 표시**가 오도록 함
- 단, **단어 사이**에 사용할 땐 **\*\*\*만** 써야 함

    |markdown|rendered|
    |:---:|:---:|
    |\*\*\*Italicized bold text\*\*\*|***Italicized bold text***|
    |\_\_\_Italicized bold text\_\_\_|___Italicized bold text___|
    |\*\*\_Italicized bold text\_\*\*|**_Italicized bold text_**|
    |\_\_\*Italicized bold text\*\_\_|__*Italicized bold text*__|
    |Italicized\*\*\*bold\*\*\*text|Italicized***bold***text|

<br><br>

## ***5. Blockquote***

- **blockquote**를 표현하기 위해 사용  
- **단락 앞에 \>를** 붙임

      > I'm in blockquote  

- blockquote 안에서 **단락**을 표현할 땐 **단락 사이에 빈줄**을 넣고 **앞에 >을** 붙임

      > First paragraph in blockquote  
      >  
      > Second paragraph in blockquote  

- **중첩된 blockquote**를 사용할 땐 **중첩되는 블록 앞에 >>을** 붙여주면 됨

      > Blockquote  
      >> Nested blockquote  

- blockquote 안에는 **다양한 문법 요소들**이 사용될 수 있음
- 어떤 게 사용 가능한지는 **직접 확인**해봐야 함

      > ## Heading  
      >  
      > - list 1  
      > - list 2  
      >  
      > **Bold** and *Italicized*  

<br><br>

## ***6. List***

- ## *Ordered List*  

    - **순차적으로 번호가 붙은 목록**를 표현할 때 사용  
    - 각 아이템 **앞에 번호와 마침표**를 붙임
    - 앞에 붙는 번호가 꼭 순차적일 필요는 없지만, **반드시 1로 시작**해야 함  
    - 리스트 안에서 **4칸 스페이스나 탭 한 번** 하면 **indented list**도 표현할 수 있음  

          1. first item
          2. second item
              1. indented one
              2. indented two
          3. third item
        
          1. first item  
          4. second item  
          2. third item  
  
          1. first item  
          1. second item  
          1. third item  

<br>

- ## *Unordered List*

    - **순서가 없는 목록**을 표현할 때 사용
    - 각 아이템 앞에 **\-이나 \*, \+을** 붙임
    - 리스트 안에서 **4칸 스페이스나 탭 한 번** 하면 **indented list**도 표현할 수 있음  
    - 같은 리스트를 표현할 땐 **기호를 통일**시키는 것을 권장

          - first item
          - second item
              - indented one
              - indented two
          - third item
        
          * first item  
          * second item  
          * third item  
  
          + first item  
          + second item  
          + third item  

<br>

- **리스트 안에 다른 문법 요소**를 추가할 수 있음  
- **paragraph, blockquote, code block, image, nested list** 등
- 추가할 땐 스페이스나 탭으로 **4칸 들여써야** 함  
- **code block**을 사용할 땐 **보통 4칸** 들여쓰지만, **리스트 안에서는 8칸** 들여써야 함

      - first item
      - second item
      
          a paragraph
      
      - third item

          > a blockquote
      
      - fourth item  

              <html>
                <head>
                  <title>Test</title>
                </head>
      
      - fifth item

          ![What's Markdown?](https://d33wubrfki0l68.cloudfront.net/722f0d393d543949f94038accfbb3887ba9c318b/f6fc0/assets/images/atom.png)
      
      - sixth item  
          1. one
          2. two  

<br><br>

## ***7. Code***

- 단어나 구를 **코드**로 나타낼 때는 **앞뒤에 `을** 붙임
- 코드로 나타내려는 단어나 구에 이미 **`이 포함되어 있다면 ``을** 사용

      `This is code`
      `` This is `code` ``

- **code block**을 만드려면, 스페이스나 탭으로 **4칸을 들여씀**

          <html>
            <head>
            </head>
          </html>

<br><br>

## ***8. Horizontal Rule***

- **수평선**을 만들 때 사용
- **세 개 이상의 *이나 -, _로 라인**을 구성 (어느 걸로 하든 모양은 동일)
- 잘못하면 Heading이 될 수도 있기 때문에 **빈 줄을 위 아래로** 넣는 것이 좋음

      ***
      ---
      _________

      Try to put a blank line before...

      ---

      ...and after a horizontal rule.

<br><br>

## ***9. Link***

- **링크**를 생성할 땐, **링크가 걸릴 텍스트를 대괄호로** 감싼 후, 옆에 **URL을 괄호로** 묶어주면 됨
- **URL에는 빈 칸이 있으면 안 됨**. **%20**으로 빈칸을 채워줘야 함

      [Usaint](https://saint.ssu.ac.kr)
      [Heading](#1.%20Heading)

- 링크에 **타이틀**을 추가할 수도 있음
- 타이틀을 추가하면 마우스 커서로 링크를 가리킬 때 **툴팁**이 뜸
- 타이틀은 **" "로** 감싸진 형태로 **URL 옆에** 위치함

      [Usaint](https://saint.ssu.ac.kr "Soongsil University")

- **URL이나 이메일**을 **링크로 변환**시키는 것도 가능
- URL이나 이메일을 **꺽쇠괄호로 묶어**주면 됨

      <https://saint.ssu.ac.kr>
      <email@example.com>

- **링크를 강조**하거나, **코드**로 나타내는 것도 가능

      **[Usaint](https://saint.ssu.ac.kr)**
      *[Usaint](https://saint.ssu.ac.kr)*
      [`Usaint`](https://saint.ssu.ac.kr)

<br>

- ## *Reference-style Link*
    - 마크다운은 **링크가 걸린 텍스트와 URL을 분리**해서 저장할 수 있는 **레퍼런스 스타일의 링크**도 지원
    - reference-style link는 **총 두 부분**으로 구성됨. **(1)본문의 링크가 걸린 텍스트 부분**과 **(2)문서 어딘가에 URL이 저장된 부분**
    
    <br>

    - (1)은 **두 개의 대괄호 묶음**으로 구성됨  
    - 첫 번째 대괄호에는 **링크가 걸릴 텍스트**가, 두 번째 대괄호에는 (1)을 (2)와 연결해줄 **인덱스**가 들어감  
    - 인덱스에는 **문자나 숫자, 스페이스나 마침표**가 들어갈 수 있음  
    - **두 대괄호 묶음 사이를 띄어쓰는** 것도 가능  

          [Markdown Guide][1]
          [Markdown Guide] [2]

    - (2)은 **대괄호로 묶은 인덱스 옆에 :을** 찍고 **최소 한 칸 띄어쓰기** 한 후 **URL**을 적으면 됨
    - URL을 **꺽쇠 괄호**로 묶는 것 가능
    - **" "나 ' ', ( )로 타이틀**을 추가할 수도 있음
          
          [1]: https://www.markdownguide.org
          [1]: https://www.markdownguide.org "Guide of Markdown"
          [1]: https://www.markdownguide.org 'Guide of Markdown'
          [1]: https://www.markdownguide.org (Guide of Markdown)
          [1]: <https://www.markdownguide.org> "Guide of Markdown"
          [1]: <https://www.markdownguide.org> 'Guide of Markdown'
          [1]: <https://www.markdownguide.org> (Guide of Markdown)

    - (2)는 **문서 어느 곳에나** 위치할 수 있음
    - **단락 바로 밑**에 적기도 하고, **각주나 미주처럼** 달기도 함

          This is [reference-style link][2]. The second part of the link is placed below this paragraph.

          [2]: https://www.markdownguide.org/basic-syntax/#reference-style-links "Reference-style Link"

<br><br>

## ***10. Image***

- 마크다운에서의 **이미지 삽입** 문법은 기본적으로 **![](이미지 주소)** 이런 형태를 띔
- 위 **대괄호에는 alt 속성**이 들어감 (이미지 경로에 오류가 있을 때 이미지 대신 띄어주는 텍스트)
- **타이틀을 " "로 묶어 이미지 주소 옆에** 배치하면 타이틀이 추가됨


      ![](https://d33wubrfki0l68.cloudfront.net/722f0d393d543949f94038accfbb3887ba9c318b/f6fc0/assets/images/atom.png)

      ![What's Markdown?](https://d33wubrfki0l68.cloudfront.net/722f0d393d543949f94038accfbb3887ba9c318b/f6fc0/assets/images/atom.png)

      ![What's Markdown?](https://d33wubrfki0l68.cloudfront.net/722f0d393d543949f94038accfbb3887ba9c318b/f6fc0/assets/images/atom.png "What is Markdown?")

- **이미지에 링크**를 거는 것도 가능
- **이미지 문법을 대괄호**로 묶고 **옆에 소괄호로 묶은 URL**을 배치하면 됨

      [![What's Markdown?](https://d33wubrfki0l68.cloudfront.net/722f0d393d543949f94038accfbb3887ba9c318b/f6fc0/assets/images/atom.png "What is Markdown?")](https://www.markdownguide.org/getting-started/)

<br><br>

## ***11. Escaping Character***

- 마크다운에서 텍스트 형식을 지정하는 데 쓰이는 리터럴 문자를 표시할 때는 \을 씀

      \* Without backslash, this would be a list

- The Table of Characters You Can Escape  

    | Character | Name |
    |:---:|:---:|
    | \\ | backslash |
    | \` | backtick |
    | \* | asterisk |
    | \_ | underscore |
    | \{} | curly braces |
    | \[] | brackets |
    | \<> | angle brackets |
    | \() | parentheses |
    | \# | pound sign |
    | \+ | plus sign |
    | \- | minus sign(hyphen) |
    | \. | dot |
    | \! | exclamation mark |
    | \| | pipe |

<br><br>

## ***12. HTML***

- 대부분의 마크다운 어플리케이션은 HTML 태그를 지원함
- HTML 태그는 텍스트 색상을 지정하거나 이미지 너비를 변경하는 등 요소의 속성을 바꾸는데 유용

      This <em>word</em> is italic.

- **블록 레벨의 HTML 요소**(\<div>, \<table>, \<pre>, \<p> 등)을 사용할 땐 **위 아래로 공백**을 넣어 주변과 분리시킴
- 형식 지정에 방해가 될 수 있는 **탭이나 스페이스는 자제**해야 됨
- **HTML 블록 내**에선 **마크다운 문법 사용 불가**
