 <H3>NAME: THAJESH  K</H3>
<H3>REGISTER NO.: 212223230229</H3>
<H3>EX. NO.8</H3>
<H3>DATE:</H3>
<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>
<H3>Aim:</H3> 
 To implement the conversion of live speech to text.<BR>
<h3>Algorithm:</h3>
Step 1: Import the speech_recognition library<Br>
Step 2: Initialize the Recognizer<Br>
Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
Step 4: Set the duration for audio capture<Br>
Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
Step 6: Display a message in the console to prompt the user to speak.<Br>
Step 7: Capture audio from the default microphone<Br>
Step 9: Use the default microphone as the audio source.<Br>
Step 10: Record audio for the specified duration using the Recognizer instance.<Br>
Step 11: Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>
<H3>Program:</H3>

```
import speech_recognition as sr
import pyaudio
def record_audio():
    r=sr.Recognizer()
    r.energy_threshold = 6000
    voicedata=''
    try:
        with sr.Microphone() as source:
            audio=r.listen(source)
            voicedata=r.recognize_google(audio)            
    except sr.UnknownValueError:
        print("Unable to Recognize Audio")
    except sr.RequestError:
        print("Unable to find the Resource")
    return voicedata
while True:
    print("Say Something ....")
    text=record_audio()
    print(text)
    if text=="stop" or text=="close" or text=="exit":
        exit(1)
```

<H3> Output:</H3>

![Screenshot 2024-10-29 104213](https://github.com/user-attachments/assets/0eecc8ee-4bff-438d-8867-bbfa8df2fce9)


<H3> Result:</H3>

Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
