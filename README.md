#include <iostream>
#include <vector>
#include <cstdlib>
using namespace std;

struct laboratorio {
    string nombres;
    int cantidad, opcion;
    char tipo;
    float precio;
};

int main() {
    vector<laboratorio> datos;
    laboratorio lab;
    int opcion_menu;

    do {
        cout << "=== MENÚ PRINCIPAL ===" << endl;
        cout << "1. Ingresar instrumentos" << endl;
        cout << "2. Mostrar instrumentos" << endl;
        cout << "3. Buscar instrumento" << endl;
        cout << "4. Salir" << endl;
        cout << "Seleccione una opcion: ";
        cin >> opcion_menu;

        switch (opcion_menu) {
            case 1:
                cout << "INGRESE LA CANTIDAD DE INSTRUMENTOS" << endl;
                cin >> lab.opcion;
                for (int i = 0; i < lab.opcion; i++) {
                    laboratorio capacidad;
                    cout << "INGRESE EL NOMBRE DE SU INSTRUMENTO" << "[" << i << "]" << endl;
                    cin >> capacidad.nombres;
                    cout << "INGRESE LA CANTIDAD DE SUS INSTRUMENTOS" << "[" << i << "]" << endl;
                    cin >> capacidad.cantidad;
                    cout << "INGRESE EL TIPO DE SUS INSTRUMENTOS" << "[" << i << "]" << endl;
                    cin >> capacidad.tipo;
                    cout << "INGRESE EL PRECIO DE SU INSTRUMENTO" << "[" << i << "]" << endl;
                    cin >> capacidad.precio;
                    datos.push_back(capacidad);
                    system("cls");
                }
                break;
            case 2:
                for (size_t i = 0; i < datos.size(); i++) {
                    cout << "=============================" << endl;
                    cout << " INSTRUMENTO #" << (i + 1) << endl;
                    cout << "-----------------------------" << endl;
                    cout << " NOMBRE:   " << datos[i].nombres << endl;
                    cout << " CANTIDAD: " << datos[i].cantidad << endl;
                    cout << " TIPO:     " << datos[i].tipo << endl;
                    cout << " PRECIO:   $" << datos[i].precio << endl;
                    cout << "=============================" << endl;
                }
                break;
            case 3: 
                {
        string buscado;

        cout<< "INGRESE EL DATO A BUSCAR"<<endl;
        cin>>buscado;

            for (size_t i=0;i<datos.size();i++){
                    if (datos[i].nombres==buscado){
            cout<< "SE ENCONTRO "<<"["<<i+1<<"] :"<<buscado<<endl;
            }
                else{
            cout<< "NO ENCONTRO "<<"["<<i+1<<"] :"<<buscado<<endl;
                }
                }
                break;
            }
            case 4:
                cout << "Saliendo del programa..." << endl;
                break;
        }
    } while (opcion_menu != 4);

    return 0;
}
