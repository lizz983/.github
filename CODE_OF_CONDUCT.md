gestiona una lista de tareas

class ListaTareas:
    def _init_(self):
        self.tareas = []

    def agregar_tarea(self, tarea):
        self.tareas.append({"descripcion": tarea, "completada": False})

    def marcar_completada(self, indice):
        if indice < len(self.tareas):
            self.tareas[indice]["completada"] = True
        else:
            print("Índice de tarea inválido")

    def mostrar_tareas_pendientes(self):
        print("Tareas Pendientes:")
        for i, tarea in enumerate(self.tareas):
            if not tarea["completada"]:
                print(f"{i+1}. {tarea['descripcion']}")

def main():
    lista_tareas = ListaTareas()

    lista_tareas.agregar_tarea("Hacer la compra")
    lista_tareas.agregar_tarea("Estudiar para el examen")
    lista_tareas.agregar_tarea("Preparar la presentación")

    lista_tareas.mostrar_tareas_pendientes()

    lista_tareas.marcar_completada(1)

    lista_tareas.mostrar_tareas_pendientes()

if _name_ == "_main_":
    main()
