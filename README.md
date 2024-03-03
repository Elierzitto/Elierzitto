class Vehiculo:
    def __init__(self, tipo):
        self.tipo = tipo

class Carro(Vehiculo):
    def __init__(self, tipo, tipo_gasolina):
        super().__init__(tipo)
        self.tipo_gasolina = tipo_gasolina

class Balsa(Vehiculo):
    def __init__(self, tipo, motorizado):
        super().__init__(tipo)
        self.motorizado = motorizado

class Avion(Vehiculo):
    def __init__(self, tipo, capacidad_pasajeros):
        super().__init__(tipo)
        self.capacidad_pasajeros = capacidad_pasajeros

def mostrar_menu_principal():
    print("Menú Principal")
    print("1: Fase 1 – Objetos y recursividad")
    print("2: Fase 2")
    print("3: Fase 3")
    print("4: Salir del programa")

def mostrar_submenu_fase1():
    print("\nSubmenú Fase 1")
    print("a: Ingresar datos de vehículos")
    print("b: Mostrar datos del vehículo")
    print("c: Crear una torre de Hanoi")
    print("d: Regresar al menú principal")

def ingresar_datos_vehiculo():
    tipo_vehiculo = input("Ingrese el tipo de vehículo (carro, balsa o avión): ").lower()
    if tipo_vehiculo == "carro":
        tipo_gasolina = input("Ingrese el tipo de gasolina del carro: ")
        vehiculo = Carro(tipo_vehiculo, tipo_gasolina)
    elif tipo_vehiculo == "balsa":
        motorizado = input("¿La balsa es motorizada? (sí/no): ").lower() == "sí"
        vehiculo = Balsa(tipo_vehiculo, motorizado)
    elif tipo_vehiculo == "avión":
        capacidad_pasajeros = int(input("Ingrese la capacidad de pasajeros del avión: "))
        vehiculo = Avion(tipo_vehiculo, capacidad_pasajeros)
    else:
        print("Tipo de vehículo no válido")
        return
    print("Datos del vehículo ingresados correctamente.")

def mostrar_datos_vehiculo():
    # Aquí deberías tener un mecanismo para mostrar los datos del vehículo ingresados previamente
    print("Mostrar datos del vehículo")
    # Esto es un placeholder, necesitarás implementar la lógica correspondiente

def crear_torre_hanoi():
    print("\nCrear una torre de Hanoi")
    num_discos = int(input("Ingrese el número de discos (mínimo 3): "))
    while num_discos < 3:
        print("Debe ingresar al menos 3 discos para realizar la torre.")
        num_discos = int(input("Ingrese el número de discos (mínimo 3): "))

    def hanoi(n, origen, destino, auxiliar):
        if n == 1:
            print(origen, "-->", destino)
            return
        hanoi(n - 1, origen, auxiliar, destino)
        print(origen, "-->", destino)
        hanoi(n - 1, auxiliar, destino, origen)

    hanoi(num_discos, 1, 3, 2)

def main():
    while True:
        mostrar_menu_principal()
        opcion_principal = input("Seleccione una opción: ")

        if opcion_principal == "1":
            while True:
                mostrar_submenu_fase1()
                opcion_fase1 = input("Seleccione una opción: ")

                if opcion_fase1 == "a":
                    ingresar_datos_vehiculo()
                elif opcion_fase1 == "b":
                    mostrar_datos_vehiculo()
                elif opcion_fase1 == "c":
                    crear_torre_hanoi()
                elif opcion_fase1 == "d":
                    break
                else:
                    print("Opción no válida")
        elif opcion_principal == "2":
            # Implementación de la Fase 2
            print("Fase 2 aún no implementada")
        elif opcion_principal == "3":
            # Implementación de la Fase 3
            print("Fase 3 aún no implementada")
        elif opcion_principal == "4":
            print("¡Hasta luego!")
            break
        else:
            print("Opción no válida")

if __name__ == "__main__":
    main()
