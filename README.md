# ancient-greek-quiz.
“A terminal-based Ancient Greek quiz game in Python.”
def ask_question(question, options, answer):
    print("\n" + question)
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")
    while True:
        try:
            choice = int(input("Your answer (1-4): "))
            if 1 <= choice <= 4:
                return options[choice - 1] == answer
            else:
                print("Please choose a number between 1 and 4.")
        except ValueError:
            print("Please enter a number.")

def main():
    print("🏛️ Welcome to the Ancient Greek Quiz! 🏛️")
    score = 0

    questions = [
        {
            "question": "Who is considered the father of Western philosophy?",
            "options": ["Socrates", "Plato", "Aristotle", "Pythagoras"],
            "answer": "Socrates"
        },
        {
            "question": "What type of government did Athens have?",
            "options": ["Monarchy", "Oligarchy", "Democracy", "Tyranny"],
            "answer": "Democracy"
        },
        {
            "question": "Which epic poet wrote 'The Iliad' and 'The Odyssey'?",
            "options": ["Hesiod", "Sophocles", "Homer", "Euripides"],
            "answer": "Homer"
        },
        {
            "question": "What was the main gathering place in a Greek city called?",
            "options": ["Acropolis", "Agora", "Colosseum", "Pantheon"],
            "answer": "Agora"
        },
        {
            "question": "Which Greek god was considered the king of the gods?",
            "options": ["Apollo", "Zeus", "Poseidon", "Ares"],
            "answer": "Zeus"
        }
    ]

    for q in questions:
        if ask_question(q["question"], q["options"], q["answer"]):
            print("✅ Correct!")
            score += 1
        else:
            print(f"❌ Wrong! The correct answer was: {q['answer']}")

    print(f"\n🏁 Quiz finished! Your score: {score}/{len(questions)}")
    if score == len(questions):
        print("🎉 You are a true Ancient Greece expert!")
    elif score >= 3:
        print("👍 Good job! You know quite a bit!")
    else:
        print("📚 Time to hit the history books!")

if __name__ == "__main__":
    main()
