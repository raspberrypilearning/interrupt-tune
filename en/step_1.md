You can add code to play one tune or sound then use a button or switch to play another tune at the moment it is activated rather than waiting until the end: 

--- code ---
---
language: python
filename: sound_machine.py
line_numbers: false

---
def high_sound(): 
    speaker.play(600, 0.5) 
    sleep(0.1)

def low_sound():
    speaker.play(400, 0.5)

button.when_pressed = low_sound

while True: 
    high_sound()

--- /code ---
