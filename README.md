# software-testing-quiz_app.py
import datetime

def save_result(score, total):
timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
with open("quiz_results.txt", "a") as file:
file.write(f"[{timestamp}] Score: {score}/{total}\n")

def run_quiz():
questions = [
{"q": "Part of SDLC?", "options": ["A: Req", "B: Coding", "C: Testing", "D: None"], "answer": "D"},
{"q": "Smallest logic test?", "options": ["A: Unit", "B: Integration", "C: Acceptance", "D: Regression"], "answer": "A"},
{"q": "End user test?", "options": ["A: Unit", "B: Integration", "C: Acceptance", "D: Regression"], "answer": "C"},
{"q": "Group module test?", "options": ["A: Unit", "B: Integration", "C: Acceptance", "D: Regression"], "answer": "B"},
{"q": "Peak load test?", "options": ["A: Load", "B: Stress", "C: Endurance", "D: Pressure"], "answer": "A"},
{"q": "One framework per language?", "options": ["A: True", "B: False"], "answer": "B"},
{"q": "NOT a JS primitive?", "options": ["A: string", "B: number", "C: object", "D: undefined"], "answer": "C"},
{"q": "NOT true?", "options": ["A: Obj hold primitives", "B: '13' is string", "C: Bool is T/F", "D: Strings need \"\""], "answer": "D"},
{"q": "Test only at end?", "options": ["A: True", "B: False"], "answer": "B"},
{"q": "JS Array start index?", "options": ["A: 0", "B: 1", "C: A", "D: a"], "answer": "A"}
]
score = 0
for i, item in enumerate(questions):
print(f"\nQ{i+1}: {item['q']}")
for opt in item['options']: print(opt)
guess = input("Answer: ").upper()
if guess == item['answer']:
print("✅ Correct!"); score += 1
else: print(f"❌ Wrong. Answer: {item['answer']}")
print(f"\nFinal: {score}/{len(questions)}")
save_result(score, len(questions))

if __name__ == "__main__":
run_quiz()
