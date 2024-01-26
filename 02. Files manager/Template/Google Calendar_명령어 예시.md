[명령어 모음](https://yukigasai.github.io/obsidian-google-calendar/Commands)

### Codeblocks 예시
//```gEvent
type: day

timespan: 2 (화면에 표시되는 일수를 결정함. 주간&스케줄 보이일때 설정가능)
date: 2024-01-01 (특정날자의 일정을 불러오고 싶을때 삭제하면 오늘 날짜부터 
**보통 Templater 플러그인 명령어를 활용하여 제목에 있는 날짜를 불러옴** 안되면 date_daily:<%코드%>)
exclude: ["XXX"] (제외 시키고 싶은 캘린더 명칭을 정확하게 작성)

navigation: true
showAllDay: true
hourRange: [6, 17]
offset: 0
include: ["Personal"]
//```

### TYPE
1.  `day` : 타임라인
2. `week` : 주간보기
3. `month` : 월별보기
4. `year` : 연간보기
5. `web` : 웹뷰 열기
6. `schedule` : 일정 보기


### Ultimate Todoist Sync 플러그인 사용법 

>[!tip] 
> command + L을 눌러 체크박스 만들기   >>   할일적기   >>   #todoist 적어주기

 - [x] 옵시디언 자료 백업   \\ [link](https://todoist.com/showTask?id=7633224944) #todoist %%[todoist_id:: 7633224944]%% 

- [x] 테스트 #Developments #해야할일  [link](https://todoist.com/showTask?id=7633260199) #todoist  %%[todoist_id:: 7633260199]%%

- [x] 테스트 #Developments [link](https://todoist.com/showTask?id=7633269140) #todoist  %%[todoist_id:: 7633269140]%%
	- [x] 하위 할일 [link](https://todoist.com/showTask?id=7633273088) #todoist  %%[todoist_id:: 7633273088]%%

- [x] 중요도 !!4 #Developments [link](https://todoist.com/showTask?id=7633275456) #todoist  %%[todoist_id:: 7633275456]%% 
!!4 , !!3 , !!2 , !!1 순서로 4가 가장 중요