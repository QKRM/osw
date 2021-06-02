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
24~40번째 줄에서 색들의 rgb값을 할당하고, 46,47에서 colors 로 저장   
377~398 getNewPiece()함수를 통해 각각의 블록에 각각의 색깔을 할당하게 함.   
    
```python
#24~40,46~47
#               R    G    B
WHITE       = (255, 255, 255)
GRAY        = (185, 185, 185)
BLACK       = (  0,   0,   0)
RED         = (155,   0,   0)
LIGHTRED    = (175,  20,  20)
GREEN       = (  0, 155,   0)
LIGHTGREEN  = ( 20, 175,  20)
BLUE        = (  0,   0, 155)
LIGHTBLUE   = ( 20,  20, 175)
YELLOW      = (155, 155,   0)
LIGHTYELLOW = (175, 175,  20)
SKYBLUE     = (  0, 153, 244)
LIGHTSKYBLUE= (204, 235, 255)
PINK        = (255,102,255)
LIGHTPINK   = (255,204,255)
BROWN       = (102,51,0)
LIGHTBROWN  = (255,217,179)


COLORS      = (     BLUE,      GREEN,      RED,      YELLOW, SKYBLUE,PINK,BROWN)
LIGHTCOLORS = (LIGHTBLUE, LIGHTGREEN, LIGHTRED, LIGHTYELLOW,LIGHTSKYBLUE,LIGHTPINK,LIGHTBROWN)

#377 getNewPiece()
if shape == 'S':
        colors = 0
    elif shape == 'Z':
        colors = 1
    elif shape == 'J':
        colors = 2
    elif shape == 'L':
        colors = 3
    elif shape == 'I':
        colors = 4
    elif shape == 'O':
        colors = 5
    elif shape == 'T':
        colors = 6
    newPiece = {'shape': shape,
                'rotation': random.randint(0, len(PIECES[shape]) - 1),
                'x': int(BOARDWIDTH / 2) - int(TEMPLATEWIDTH / 2),
                'y': -2, # start it above the board (i.e. less than 0)
                'color': colors}
```

