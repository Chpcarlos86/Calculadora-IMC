# Calculadora-IMC
Tarea de Ucamp

El proyecto de hacer una calculadora de IMC me fue un reto importante ya que no tengo ninguna experiencia en programacion, la orientacion que me dieron fue de ayuda pero fue necesario investigar para poder realizar un buen trabajo en el proyecto

Estoy emocionado por seguir aprendiendo programacion




def solicitar_dato(mensaje, tipo="texto"):
    while True:
        dato = input(mensaje).strip()
        if not dato:
            print("Error: Este campo no puede quedar vacío. Intente de nuevo.")
            continue
        if tipo == "numero":
            try:
                dato = float(dato)
                if dato <= 0:
                    print("Error: Ingrese un valor mayor a cero.")
                    continue
                return dato
            except ValueError:
                print("Error: Debe ingresar un valor numérico válido. Intente de nuevo.")
        elif tipo == "entero":
            try:
                dato = int(dato)
                if dato <= 0:
                    print("Error: Ingrese un valor entero mayor a cero.")
                    continue
                return dato
            except ValueError:
                print("Error: Debe ingresar un valor entero. Intente de nuevo.")
        else:
            return dato

# Solicitar datos con validación
nombre = solicitar_dato("Nombre: ")
edad = solicitar_dato("Tu edad: ", tipo="entero")
peso = solicitar_dato("Tu peso en Kg: ", tipo="numero")
altura = solicitar_dato("Tu altura en metros: ", tipo="numero")

# Cálculo del IMC
imc = peso / pow(altura, 2)
imc = round(imc, 2)

# Mostrar el IMC y clasificación
print(f"\nNombre: {nombre}")
print(f"Edad: {edad} años")
print(f"Peso: {peso} kg")
print(f"Altura: {altura} m")
print(f"Tu IMC es: {imc}")

# Clasificación del IMC
if imc < 18.5:
    print("Clasificación: Bajo de peso")
elif imc <= 24.99:
    print("Clasificación: Peso normal")
elif imc <= 29.99:
    print("Clasificación: Sobrepeso")
elif imc <= 34.99:
    print("Clasificación: Obesidad I")
elif imc <= 39.99:
    print("Clasificación: Obesidad II")
else:
    print("Clasificación: Obesidad mórbida")



