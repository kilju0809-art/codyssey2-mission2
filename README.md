# 🌍 세계수도·역사 퀴즈 게임

터미널에서 즐기는 콘솔 기반 퀴즈 게임입니다.

## 📖 프로젝트 개요
세계 여러 나라의 **수도**와 **역사** 상식을 묻는 퀴즈 게임입니다.
Python과 Git을 학습하기 위해 만들었으며,
퀴즈를 풀며 세계 지리·역사 지식을 재미있게 익힐 수 있습니다.

[#세계수도알아보기 퀴즈]
## 🎲 퀴즈 주제 선정 이유
- **주제**: 세계수도·역사
- **선정 이유**:
  [평소 여행과 학습을 좋아하는 퀴즈]
  ## ▶️ 실행 방법
1. 저장소를 복제합니다.
   ```bash
   git clone [저장소 주소]
   cd [폴더 이름]
   python main.py
   
---

**💡 작성 팁**
- `[저장소 주소]`는 본인의 GitHub 저장소 주소로 바꿔주세요
- `[폴더 이름]`도 실제 폴더 이름으로 바꿔주세요
- 실행 파일 이름(`main.py`)은 **나중에 코드를 만들 때 정할 이름**이에요. 지금은 `main.py`로 두고, 나중에 달라지면 그때 수정하면 됩니다 😊

---

> ⚠️ 아직 코드 파일은 안 만들었으니, 지금은 **README에 실행 방법을 적어두는 것**까지만 하면 돼요!

작성 다 하셨으면 **"다음"**이라고 알려주세요! 👍
## ⚙️ 기능 목록
- [ ] 퀴즈 문제 출제 (세계수도·역사)
- [ ] 사용자 답 입력받기
- [ ] 정답/오답 판별
- [ ] 점수 계산
- [ ] 최종 결과 출력
git add README.md
git commit -m "docs: README 작성 (개요, 주제, 실행방법, 기능목록)"
git add README.md
git commit -m "docs: README 작성 (개요, 주제, 실행방법, 기능목록)"
class Quiz:
    def __init__(self, question, answer):
        self.question = question
        self.answer = answer
q1 = Quiz("프랑스의 수도는?", "파리")

print(q1.question)   # 프랑스의 수도는?
print(q1.answer)     # 파리
class Quiz:
    def __init__(self, question, answer):
        self.question = question
        self.answer = answer

    def check(self, user_answer):
        return user_answer == self.answer
        q1 = Quiz("프랑스의 수도는?", "파리")

print(q1.check("파리"))    # True  ✅ 맞음!
print(q1.check("런던"))    # False ❌ 틀림!
class Quiz:
    def __init__(self, question, answer):
        self.question = question
        self.answer = answer

    def check(self, user_answer):
        return user_answer == self.answer


# --- 여기부터 테스트 코드 ---
q1 = Quiz("프랑스의 수도는?", "파리")

print(q1.question)          # 질문이 잘 저장됐나?
print(q1.check("파리"))      # 정답일 때 True 나오나?
print(q1.check("런던"))      # 오답일 때 False 나오나?
python quiz_game.py
프랑스의 수도는?
True
False
class QuizGame:
    def __init__(self):
        self.quizzes = []   # 문제들을 담을 빈 리스트
        self.score = 0      # 시작 점수는 0점
game = QuizGame()
print(game.quizzes)   # []    빈 리스트
print(game.score)     # 0     시작 점수
class QuizGame:
    def __init__(self):
        self.quizzes = []
        self.score = 0

    def add_quiz(self, quiz):          # 👈 추가된 부분
        self.quizzes.append(quiz)
        # 문제 만들기
q1 = Quiz("프랑스의 수도는?", "파리")
q2 = Quiz("일본의 수도는?", "도쿄")

# 게임 만들고 문제 추가하기
game = QuizGame()
game.add_quiz(q1)
game.add_quiz(q2)

print(len(game.quizzes))   # 2  → 문제 2개 들어갔나?
2
    def start(self):
        for quiz in self.quizzes:           # 문제를 하나씩 꺼내서
            user_answer = input(quiz.question + " ")   # 질문 보여주고 답 입력받기
            if quiz.check(user_answer):     # 정답인지 확인
                print("정답입니다! 🎉")
                self.score += 1             # 점수 1 올리기
            else:
                print("틀렸습니다. 정답은", quiz.answer)

        print(f"\n게임 종료! 총 {len(self.quizzes)}문제 중 {self.score}개 맞혔어요!")
        q1 = Quiz("프랑스의 수도는?", "파리")
q2 = Quiz("일본의 수도는?", "도쿄")

game = QuizGame()
game.add_quiz(q1)
game.add_quiz(q2)

game.start()   # 게임 시작!
프랑스의 수도는? 파리
정답입니다! 🎉
일본의 수도는? 서울
틀렸습니다. 정답은 도쿄

게임 종료! 총 2문제 중 1개 맞혔어요!
# 게임 생성
game = QuizGame()

# 세계 수도 & 역사 문제 추가
game.add_quiz(Quiz("프랑스의 수도는?", "파리"))
game.add_quiz(Quiz("일본의 수도는?", "도쿄"))
game.add_quiz(Quiz("미국의 수도는?", "워싱턴"))
game.add_quiz(Quiz("훈민정음을 창제한 조선의 왕은?", "세종대왕"))
game.add_quiz(Quiz("임진왜란이 일어난 세기는? (예: 16)", "16"))

# 게임 시작!
game.start()
game.add_quiz(Quiz("프랑스의 수도는?", "파리"))
class Quiz:
    def __init__(self, question, answer):
        ...
    def check(self, user_answer):
        ...

class QuizGame:
    def __init__(self):
        ...
    def add_quiz(self, quiz):
        ...
    def start(self):
        ...

# 게임 실행 부분
game = QuizGame()
game.add_quiz(...)
...
game.start()
