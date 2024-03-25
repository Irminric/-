# -
情感互动利用情感识别技术和自然语言处理,让智能家居设备能够理解和响应用户的情感需求,提供更加人性化和贴心的家居交互体验。
from textblob import TextBlob
import random

# Simple Emotion Recognition Function Based on Sentiment Analysis
def recognize_emotion(input_text):
    blob = TextBlob(input_text)
    polarity = blob.sentiment.polarity
    if polarity > 0.2:
        return "happy"
    elif polarity < -0.2:
        return "sad"
    else:
        return "neutral"

# Smart Home Action Simulation Based on Emotion
def smart_home_action(emotion):
    actions = {
        "happy": "Playing your favorite upbeat playlist.",
        "sad": "Dimming the lights and playing soothing music.",
        "neutral": "Maintaining a neutral room atmosphere."
    }
    return actions.get(emotion, "Not sure how to respond. Keeping everything as is.")

# Main Interaction Flow
def main():
    print("Hello! How was your day?")
    user_input = input()
    user_emotion = recognize_emotion(user_input)
    print(f"It seems you're feeling {user_emotion} today.")
    action = smart_home_action(user_emotion)
    print(action)

if __name__ == "__main__":
    main()
