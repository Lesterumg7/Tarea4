# Tarea4
Tarea de algoritmos 4 

# Ejercicio 1 (Pyhton) 
import random

def generar_vector(length):
    return [random.randint(1, 100) for _ in range(length)]

# Solicitar al usuario la longitud de los vectores
longitud = int(input("Ingrese la longitud de los vectores: "))

# Generar dos vectores aleatorios
vector_a = generar_vector(longitud)
vector_b = generar_vector(longitud)

# Sumar los valores de los vectores
suma_a = sum(vector_a)
suma_b = sum(vector_b)

print("Vector A:", vector_a)
print("Vector B:", vector_b)
print("Suma de los valores en el vector A:", suma_a)
print("Suma de los valores en el vector B:", suma_b)

# Verificar los escenarios
if suma_a == suma_b:
    print("Los vectores son iguales.")
elif suma_a < suma_b:
    print("El vector A es menor que el vector B.")
else:
    print("El vector B es menor que el vector A.")  

Ejercicio en c++  
#include <iostream>
#include <vector>
#include <ctime>
#include <cstdlib>

// Función para generar un vector aleatorio de longitud 'length'
std::vector<int> generarVector(int length) {
    std::vector<int> vec;
    for (int i = 0; i < length; ++i) {
        vec.push_back(rand() % 100 + 1); // Números aleatorios entre 1 y 100
    }
    return vec;
}

int main() {
    srand(static_cast<unsigned>(time(0))); // Inicializar la semilla para números aleatorios

    int longitud;
    std::cout << "Ingrese la longitud de los vectores: ";
    std::cin >> longitud;

    // Generar dos vectores aleatorios
    std::vector<int> vectorA = generarVector(longitud);
    std::vector<int> vectorB = generarVector(longitud);

    // Calcular la suma de los valores en los vectores
    int sumaA = 0;
    int sumaB = 0;
    for (int i = 0; i < longitud; ++i) {
        sumaA += vectorA[i];
        sumaB += vectorB[i];
    }

    std::cout << "Vector A: ";
    for (int i = 0; i < longitud; ++i) {
        std::cout << vectorA[i] << " ";
    }
    std::cout << std::endl;

    std::cout << "Vector B: ";
    for (int i = 0; i < longitud; ++i) {
        std::cout << vectorB[i] << " ";
    }
    std::cout << std::endl;

    std::cout << "Suma de los valores en el vector A: " << sumaA << std::endl;
    std::cout << "Suma de los valores en el vector B: " << sumaB << std::endl;

    // Verificar los escenarios
    if (sumaA == sumaB) {
        std::cout << "Los vectores son iguales." << std::endl;
    } else if (sumaA < sumaB) {
        std::cout << "El vector A es menor que el vector B." << std::endl;
    } else {
        std::cout << "El vector B es menor que el vector A." << std::endl;
    }

    return 0;
}

# Ejercicio 2 (Python)  
def calcularSubsidio(num_hijos, edades_hijos, madre_viuda):
    subsidio_base = 0

    if num_hijos <= 2:
        subsidio_base = 70.00
    elif num_hijos <= 5:
        subsidio_base = 90.00
    else:
        subsidio_base = 120.00

    subsidio_edad_escolar = 10.00 * sum(1 for edad in edades_hijos if 6 <= edad <= 18)
    subsidio_madre_viuda = 20.00 if madre_viuda else 0.00

    subsidio_total = subsidio_base + subsidio_edad_escolar + subsidio_madre_viuda
    return subsidio_total

# Ejemplo de uso:
num_hijos = int(input("Ingrese la cantidad de hijos: "))
edades_hijos = [int(x) for x in input("Ingrese las edades de los hijos separadas por espacios: ").split()]
madre_viuda = input("¿La madre de familia es viuda? (Sí/No): ").strip().lower() == "sí"

monto_subsidio = calcularSubsidio(num_hijos, edades_hijos, madre_viuda)
print(f"El monto mensual del subsidio familiar es de Q.{monto_subsidio:.2f}") 

# Ejercicio 3 (Python)  
# Pregunta al usuario cuántos datos serán ingresados
num_datos = int(input("Ingrese la cantidad de datos: "))

# Inicializa listas para almacenar los datos
datos = []

# Pide al usuario ingresar los datos uno por uno
for i in range(num_datos):
    dato = float(input(f"Ingrese el dato {i + 1}: "))
    datos.append(dato)

# Calcula el rango de los datos
rango = max(datos) - min(datos)

# Imprime el resultado
print(f"El rango de los datos es: {rango}") 

Ejercicio 3 (c++) 
#include <iostream>
#include <vector>
#include <limits>

using namespace std;

int main() {
    // Pregunta al usuario cuántos datos serán ingresados
    int num_datos;
    cout << "Ingrese la cantidad de datos: ";
    cin >> num_datos;

    // Inicializa un vector para almacenar los datos
    vector<double> datos;

    // Pide al usuario ingresar los datos uno por uno
    for (int i = 0; i < num_datos; ++i) {
        double dato;
        cout << "Ingrese el dato " << i + 1 << ": ";
        cin >> dato;
        datos.push_back(dato);
    }

    // Calcula el rango de los datos
    double maximo = numeric_limits<double>::min();
    double minimo = numeric_limits<double>::max();

    for (int i = 0; i < num_datos; ++i) {
        if (datos[i] > maximo) {
            maximo = datos[i];
        }
        if (datos[i] < minimo) {
            minimo = datos[i];
        }
    }

    double rango = maximo - minimo;

    // Imprime el resultado
    cout << "El rango de los datos es: " << rango << endl;

    return 0;
}

Ejercicio 4 (c++) 
#include <iostream>

using namespace std;

int main() {
    int lado;
    
    // Solicitar al usuario ingresar el lado del cuadrado
    cout << "Ingrese la longitud del lado del cuadrado: ";
    cin >> lado;
    
    // Dibujar el cuadrado
    for (int i = 0; i < lado; i++) {
        if (i == 0 || i == lado - 1) {
            // Primera y última fila: imprimir asteriscos en todas las columnas
            for (int j = 0; j < lado; j++) {
                cout << "* ";
            }
            cout << endl;
        } else {
            // Filas intermedias: imprimir asterisco solo en la primera y última columna
            cout << "*";
            for (int j = 0; j < lado - 2; j++) {
                cout << "  ";
            }
            cout << " *" << endl;
        }
    }
    
    return 0;
}

Ejercicio 4 (python) 
# Solicitar al usuario ingresar el lado del cuadrado
lado = int(input("Ingrese la longitud del lado del cuadrado: "))

# Dibujar el cuadrado
for i in range(lado):
    if i == 0 or i == lado - 1:
        # Primera y última fila: imprimir asteriscos en todas las columnas
        print("* " * lado)
    else:
        # Filas intermedias: imprimir asterisco solo en la primera columna
        print("*" + "  " * (lado - 2) + " *")



