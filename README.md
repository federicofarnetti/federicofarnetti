ort random
import re

        
cinquina_lista = []

while True:
    numero_generato = random.randint(1, 90)
    if numero_generato not in cinquina_lista:
        cinquina_lista.append(numero_generato)
        print(numero_generato)
    if len(cinquina_lista) == 5:
        break

regex_numero = "^\d+$"
cinquina_utente = []
while True:

    numero_giocato = input("Numero: ")

    if re.search(regex_numero, numero_giocato):
        if int(numero_giocato) not in cinquina_utente and int(numero_giocato) >= 1 and int(numero_giocato) <= 90:
            cinquina_utente.append(int(numero_giocato))
    if len(cinquina_utente) == 5:
        break


indovinati = 0

for numero in cinquina_utente:
    if numero in cinquina_lista:
        indovinati += 1


if indovinati == 2:
    print("Complimenti. hai fatto AMBO")
elif indovinati == 3:
    print("Complimenti. hai fatto TERNO")
elif indovinati == 4:
    print("Complimenti. hai fatto QUATERNA")
elif indovinati == 5:
    print("Complimenti. hai fatto CINQUINA")
else:
    print("Hai perso!")
    # regex_n = "^\d+$"
    # numero_giocato = input("Numero:")
    # match = re.search(regex_n, numeri_da_generare)
