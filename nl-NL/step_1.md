Als je een heel deuntje wilt spelen en het wilt onderbreken voordat het is afgelopen, kun je een deuntje maken als een lijst met noten en tijdsduren en dan `play` gebruiken met `wait=False`. Hiermee kun je het deuntje stoppen of een ander deuntje afspelen door op dezelfde of een andere knop te drukken:

--- code ---
---
language: python filename: sound_machine.py line_numbers: false

---
BEAT = 0.4

liten_mus = [ ['d5', BEAT / 2], ['d#5', BEAT / 2], ['f5', BEAT], ['d6', BEAT], ['a#5', BEAT], ['d5', BEAT], ['f5', BEAT], ['d#5', BEAT], ['d#5', BEAT], ['c5', BEAT / 2],['d5', BEAT / 2], ['d#5', BEAT], ['c6', BEAT], ['a5', BEAT], ['d5', BEAT], ['g5', BEAT], ['f5', BEAT], ['f5', BEAT], ['d5', BEAT / 2], ['d#5', BEAT / 2], ['f5', BEAT], ['g5', BEAT], ['a5', BEAT], ['a#5', BEAT], ['a5', BEAT], ['g5', BEAT], ['g5', BEAT], ['', BEAT / 2], ['a#5', BEAT / 2], ['c6', BEAT / 2], ['d6', BEAT / 2], ['c6', BEAT / 2], ['a#5', BEAT / 2], ['a5', BEAT / 2], ['g5', BEAT / 2], ['a5', BEAT / 2], ['a#5', BEAT / 2], ['c6', BEAT], ['f5', BEAT], ['f5', BEAT], ['f5', BEAT / 2], ['d#5', BEAT / 2], ['d5', BEAT], ['f5', BEAT], ['d6', BEAT], ['d6', BEAT / 2], ['c6', BEAT / 2], ['b5', BEAT], ['g5', BEAT], ['g5', BEAT], ['c6', BEAT / 2], ['a#5', BEAT / 2], ['a5', BEAT], ['f5', BEAT], ['d6', BEAT], ['a5', BEAT], ['a#5', BEAT * 1.5] ]

sound = [ [523, 0.1], [None, 0.1], [523, 0.4] ]

def annoying_sound(): speaker2.play(sound, wait=False) # don't delay the main code

button.when_pressed = annoying_sound

try: speaker.play(liten_mus) finally: speaker.off() # turns speaker off when code is stopped by user speaker2.off() # turns speaker2 off when code is stopped by user

--- /code ---
