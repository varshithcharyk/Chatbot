import re

def chatbot():
    print("Chatbot: Hi! How can i help you today?")

    while True:
        user_input = input("You:").strip().lower()

        # Exit condition
        if user_input in ["exit","quit","bye"]:
            print("chatbot: Goodbye! Have a great day!")
            break

        # Rule-based responses
        elif re.search(r'\bhello\b|\bhi\b|\bhey\b', user_input):
            print("Chatbot: Hello! How can I assist you today?")

        elif re.search(r'\bhow are you\b', user_input):    
            print("Chatbot: I'm just a program, but I'm here to help! How can I assist you?")

        elif re.search(r'\bwhat is your name\b|\bhow are you\b', user_input):
            print("I'm a simple rule-based cahtbot. What's on your mind?")

        elif re.search(r'\bweather\b', user_input):
            print("Chatbot: I'm not connected to live weather data, but it might besunny or rainy depending on where you are!'") 

        elif re.search(r'\btime\b', user_input):
            from datetime import datetime
            current_time = datetime.now().strftime("%H:%M:%S")
            print(f"Chatbot: The current time is {current_time}.")

        elif re.search(r'\bhelp\b', user_input):
            print("Chatbot: Sure! I can assist you with simple queries. Try asking about the weather, time, or just say hello!")

        else:
            print("Chatbot: I'm sorry, I didn't understand that. can you rephrase?")

# Run the chatbot
if __name__ == "__main__":
    chatbot()
