
> [!tip]
> 명령어 확인 (Replace Templates) : Commend + R  
> *사용후 undo 필수*

## tp_file
### 노트 생성 날짜
<% tp.file.creation_date("YYYY-MM-DD a H시m분") %>
<% tp.file.creation_date("YYYY년 MM월 DD일 a H시m분") %>
### 노트 제목
- <% tp.file.title %>
- **슬라이스** (지정한 숫자가 글자수)
	1. <% tp.file.title.slice(7) %> ((숫자)이후로 보여줌)
	2. <% tp.file.title.slice(0,6) %>((숫자,숫자)까지 보여줌)
- **스플릿** ("" 안의 기호를 기준)
	1. <% tp.file.title.split("_")[2] %>

### 노트 저장 폴더
<% tp.file.folder() %>
### 노트의 PC 경로
<% tp.file.path() %>


## tp_date
<% tp.date.now("YYYY-MM-DD") %>
<% tp.date.tomorrow("YYYY-MM-DD") %>
<% tp.date.yesterday("YYYY-MM-DD") %>
일<% tp.date.weekday("YYYY-MM-DD", 0) %> 
월<% tp.date.weekday("YYYY-MM-DD", 1) %> 
화<% tp.date.weekday("YYYY-MM-DD", 2) %> 
수<% tp.date.weekday("YYYY-MM-DD", 3) %> 
목<% tp.date.weekday("YYYY-MM-DD", 4) %> 
금<% tp.date.weekday("YYYY-MM-DD", 5) %> 
토<% tp.date.weekday("YYYY-MM-DD", 6) %> 

## tp_system

### 클립 보드 (복사 데이터 를 나타내주는 기능)
<% tp.system.clipboard() %>

### 드롭다운 메뉴
<% tp.system.suggester(
["별5개", "별4개", "별3개", "별2개", "별1개"],
["⭐️⭐️⭐️⭐️⭐️", "⭐️⭐️⭐️⭐️", "⭐️⭐️⭐️", "⭐️⭐️", "⭐️"]
) %>

### 텍스트 필드
<% tp.system.prompt("오늘의 기분은?","") %>

