Si tu veux jouer un morceau entier et pouvoir l'interrompre avant qu'il ne se termine, tu peux créer un morceau sous la forme d'une liste de notes et de durées, puis utiliser `play` avec `wait=False`. Cela te permettra d'arrêter le morceau ou de jouer un autre morceau en appuyant sur le même bouton ou sur un autre :

--- code ---
---
language: python
filename: sound_machine.py
line_numbers: false

---
RYTHME = 0.4

liten_mus = [ ['d5', RYTHME / 2], ['d#5', RYTHME / 2], ['f5', RYTHME], ['d6', RYTHME], ['a#5', RYTHME], ['d5', RYTHME],
              ['f5', RYTHME], ['d#5', RYTHME], ['d#5', RYTHME], ['c5', RYTHME / 2],['d5', RYTHME / 2], ['d#5', RYTHME],
              ['c6', RYTHME], ['a5', RYTHME], ['d5', RYTHME], ['g5', RYTHME], ['f5', RYTHME], ['f5', RYTHME], ['d5', RYTHME / 2],
              ['d#5', RYTHME / 2], ['f5', RYTHME], ['g5', RYTHME], ['a5', RYTHME], ['a#5', RYTHME], ['a5', RYTHME], ['g5', RYTHME],
              ['g5', RYTHME], ['', RYTHME / 2], ['a#5', RYTHME / 2], ['c6', RYTHME / 2], ['d6', RYTHME / 2], ['c6', RYTHME / 2],
              ['a#5', RYTHME / 2], ['a5', RYTHME / 2], ['g5', RYTHME / 2], ['a5', RYTHME / 2], ['a#5', RYTHME / 2], ['c6', RYTHME],
              ['f5', RYTHME], ['f5', RYTHME], ['f5', RYTHME / 2], ['d#5', RYTHME / 2], ['d5', RYTHME], ['f5', RYTHME], ['d6', RYTHME],
              ['d6', RYTHME / 2], ['c6', RYTHME / 2], ['b5', RYTHME], ['g5', RYTHME], ['g5', RYTHME], ['c6', RYTHME / 2],
              ['a#5', RYTHME / 2], ['a5', RYTHME], ['f5', RYTHME], ['d6', RYTHME], ['a5', RYTHME], ['a#5', RYTHME * 1.5] ]

son = [ [523, 0.1], [None, 0.1], [523, 0.4] ]

def son_ennuyeux():
    haut_parleur2.play(son, wait=False) # ne pas retarder le code principal

bouton.when_pressed = son_ennuyeux

try:
    haut_parleur.play(liten_mus)
finally:
    haut_parleur.off() # éteint le haut-parleur lorsque le code est arrêté par l'utilisateur
    haut_parleur2.off() # éteint le haut-parleur2 lorsque le code est arrêté par l'utilisateur

--- /code ---
