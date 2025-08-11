import random

def obtener_palabra():
    palabras = ["python", "programacion", "ahorcado", "desarrollo", "juego"]
    return random.choice(palabras)

def mostrar_tablero(palabra_secreta, letras_adivinadas):
    tablero = ""
    for letra in palabra_secreta:
        if letra in letras_adivinadas:
            tablero += letra + " "
        else:
            tablero += "_ "
    print("\n" + tablero.strip())

def jugar():
    palabra_secreta = obtener_palabra()
    letras_adivinadas = []
    intentos = 6
    juego_terminado = False

    while not juego_terminado:
        mostrar_tablero(palabra_secreta, letras_adivinadas)
        intento = input("Adivina una letra: ").lower()

        if intento in letras_adivinadas:
            print("Ya adivinaste esa letra. Intenta de nuevo.")
            continue

        if intento in palabra_secreta:
            letras_adivinadas.append(intento)
            print("¡Correcto!")
        else:
            letras_adivinadas.append(intento)
            intentos -= 1
            print(f"Incorrecto. Te quedan {intentos} intentos.")

        # ¿Completó la palabra?
        if all(letra in letras_adivinadas for letra in palabra_secreta):
            mostrar_tablero(palabra_secreta, letras_adivinadas)
            print(f"¡Felicidades! Has ganado. La palabra era: {palabra_secreta}")
            juego_terminado = True
        elif intentos == 0:
            print(f"Has perdido. La palabra era: {palabra_secreta}")
            juego_terminado = True

    # ¿Reintentar?
    reintentar = input("¿Quieres jugar otra vez? (s/n): ").lower()
    if reintentar == "s":
        jugar()
    else:
        print("¡Gracias por jugar! Hasta la próxima.")

if __name__ == "__main__":
    print("==== Juego del Ahorcado ====")
    jugar()
