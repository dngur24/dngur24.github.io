---
title: 팀 프로젝트 - 배경 음악 추가
date: 2024-11-27 00:00:00 +09:00

---

```python

#배경 음악 추가
        try:
            pygame.mixer.init()
            self.bg_music = pygame.mixer.music.load("_________-.mp3") #원하는 음악 파일
            pygame.mixer.music.play(loops=-1, start =0.0)
#에러 발생시 대처 (try except)        
        except pygame.error as e:
            print("pygame error",e)
        except Exception as e:
            print("can't play music now. please check again",e)

```

1. pygame을 import한 후, mixer.music.load()를 이용해 음악을 가져옴
> pygame.mixer.music.play(loops=-1)을 이용해 음악을 무한 반복 설정

2. 혹시 문제가 생길 경우 이를 잡기 위한 코드
```python
#에러 발생시 대처 (try except)        
        except pygame.error as e:
            print("pygame error",e)
        except Exception as e:
            print("can't play music now. please check again",e)
```
> 오류가 발생한 경우, vscode 터미널에서 확인 가능하도록 처리