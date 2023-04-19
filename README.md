- 👋 Hi, I’m @Phyramirxe
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Phyramirxe/Phyramirxe is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
 import speech_recognition as sr
import pyttsx3

# 音声認識エンジンを初期化する
r = sr.Recognizer()

# テキスト読み上げエンジンを初期化する
engine = pyttsx3.init()

# ユーザーによる音声入力を取得する
with sr.Microphone() as source:
    print("何か話しかけてください...")
    audio = r.listen(source)

# 音声をテキストに変換する
try:
    text = r.recognize_google(audio, language='ja-JP')
    print(f"あなたの言葉: {text}")
except:
    print("音声を認識できませんでした。もう一度お試しください。")

# テキストを読み上げる
engine.say(text)
engine.runAndWait()
