# KBC-GAME-Code

import random

def display_question(question, options):
    print(question)
    for i, option in enumerate(options, start=1):
        print(f"{i}. {option}")
    answer = int(input("Enter your choice (1/2/3/4): "))
    return answer

def check_answer(user_answer, correct_answer):
    return user_answer == correct_answer

def kbc_game(questions):
    score = 0
    for i, (question, options, correct_answer) in enumerate(questions, start=1):
        print(f"Question {i}:")
        user_choice = display_question(question, options)
        if check_answer(user_choice, correct_answer):
            print("Correct answer!\n")
            score += 1
        else:
            print("Incorrect answer! Game over.")
            break
    print(f"You scored {score} out of {len(questions)}!")

if __name__ == "__main__":
    kbc_questions = [
        ("What is the capital of India?", ["Delhi", "Mumbai", "Chennai", "Kolkata"], 1),
        ("Which gas do plants use for photosynthesis?", ["Oxygen", "Carbon dioxide", "Nitrogen", "Hydrogen"], 2),
        ("Which planet is known as the 'Red Planet'?", ["Venus", "Mars", "Jupiter", "Saturn"], 2),
        ("What is the largest mammal?", ["Elephant", "Blue whale", "Giraffe", "Lion"], 2),
        ("Who painted the Mona Lisa?", ["Leonardo da Vinci", "Vincent van Gogh", "Pablo Picasso", "Michelangelo"], 1),
         ("The International Literacy Day is observed on ?", ["Sep 8", "Nov 28","May 2", "Sep 22"], 1),
         ("The Language Of Lakshadweep. a Union Territory of India Is?",["Tamil","Hindi","Malayalam", "Telugu"], 3),
         ("In which Group Of Places Kumbha Mela is heldevery Twelve Years ?", ["Ujjain. Purl; Prayag. Haridwar","Prayag. Haridwar, Ujjain, Nasik","Rameshwaram. Purl, Badrinath. Dwarika", "Chittakoot, Ujjain, Prayag'Haridwar"], 2),
         ("Bahubali festival is related to?", ["Islam", "Hindusim", "Buddhism", "Jainism"], 4),
         ("Which of the following was the theme of the World Red Cross and Red Crescent day?", ["Dignity for all - Focus on Women", "Dignity for all - Focus on Children", "Focus on health for all","Nourishment for all-focus on children"], 2),
         ("Who is the author of 'Manas Ka-Han?", ["Khushwant Singh", "Prem Chand", "Jaya Shankar Prasad", "Amrit Lal Nagar"],4)
         ]

    random.shuffle(kbc_questions)
    kbc_game(kbc_questions)
