import random

questions = [
    {
        "question": "Which animal is known as the ship of the desert?",
        "options": ["lion", "tiger", "camel", "giraffe"],
        "correct_option": 2,
    },
    {
        "question": "rainbow consist of how many colours?",
        "options": ["7", "3", "5", "9"],
        "correct_option": 0,
    },
    {
        "question": "baby frog is known as?",
        "options": ["kitten","puppy","tadpole","cub"],
        "correct_option":2,
    },
    {
        "question": "which animal is known as the king of the jungle?",
        "options": ["sheep","panther","elephant","lion"],
        "correct_option":3
    },
    {
        "question": "name the national bird of the india?",
        "options": ["sparrow","peacock","pigeon","woodpeaker"],
        "correct_option":1
    }

]

def ask_question(question):
    print(question["question"])
    for i, option in enumerate(question["options"]):
        print(f"{i + 1}. {option}")
    user_answer = int(input("Enter the number of your answer: ")) - 1
    return user_answer == question["correct_option"]

def main():
    random.shuffle(questions)
    score = 0

    print("Welcome to the Quiz App!")
    name = input("Enter your name: ")
    print(f"Hello, {name}!\n")

    for question in questions:
        if ask_question(question):
            print("Correct!\n")
            score += 1
        else:
            print("Incorrect. The correct answer is:", question["options"][question["correct_option"]] + "\n")

    print(f"Quiz completed, {name}!")
    print(f"You got {score}/{len(questions)} questions correct.")

if __name__ == "__main__":
    main()
