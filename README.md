## Original code   
https://inventwithpython.com/pygame/chapter7.html   

## 바뀐점  
### 배경음악을 세가지중 하나 재생
174~181번줄에서 랜덤으로 노래를 하나 로드함.   
    
```python
    while True: # game loop   
        idx = random.randint(0, 2)   
        if idx == 0:   
            pygame.mixer.music.load('Hover.mp3')   
        elif idx == 1:   
            pygame.mixer.music.load('Our_Lives_Past.mp3')   
        else:   
            pygame.mixer.music.load('Platform_9.mp3')
```
### 글자색,텍스트 변경   
44~45 번줄에서 글자와 텍스트에 쓰이는 색깔을 yellow로 변경   
    
```python
TEXTCOLOR = YELLOW   
TEXTSHADOWCOLOR = YELLOW   
```
### 경과 시간 추가   
199번줄에서 start_tick변수에 게임 시작 시간을 저장. 304~305번줄에서 지난 시간을 계산하고 출력   
    
```python
#199   
start_ticks = pygame.time.get_ticks()   
#304   
elapsed_time = (pygame.time.get_ticks() - start_ticks) / 1000   
timer = BASICFONT.render(str('Play Time: ' + str(int(elapsed_time)) + ' sec'), True, TEXTCOLOR)   
```
### 디스플레이의 이름 변경   
171번줄 `pygame.display.set_caption('2019018104 seojaehyeon')`  을 통해 디스플레이 이름 변경
### 블록의 색깔을 7가지 모양에 각각 할당하기   
