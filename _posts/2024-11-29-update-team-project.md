---
title: 팀 프로젝트 - 배경 음악 추가
date: 2024-11-27 00:00:00 +09:00

---

'''python
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
'''

