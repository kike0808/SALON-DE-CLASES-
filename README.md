# SALON-DE-CLASES-
class Estudiante:
    def __init__(self, nombre, id_estudiante):
        self.nombre = nombre
        self.id_estudiante = id_estudiante
        self.cursos_inscritos = []

    def inscribir_curso(self, curso):
        if curso.cupo_disponible() > 0:
            if all(req in self.cursos_inscritos for req in curso.requisitos_previos):
                self.cursos_inscritos.append(curso)
                curso.estudiantes.append(sel)
                print(f"{self.nombre} se ha inscrito en {curso.nombre}.")
            else:
                print(f"{self.nombre} no cumple con los requisitos previos para {curso.nombre}.")
        else:
            print(f"No hay cupo disponible en {curso.nombre}.")

# Introducir un error de estilo
class Curso:
    def __init__(self, nombre, cupo, requisitos_previos=None, horario=None, profesor=None):
        self.nombre = nombre
        self.cupo = cupo
        self.requisitos_previos = requisitos_previos if requisitos_previos else []
        self.horario = horario
        self.profesor = profesor
        self.estudiantes = []

    def cupo_disponible(self):
        return self.cupo - len(self.estudiantes)

# Introducir errores de estilo y seguridad
class Facultad:
    def __init__(self, nombre):
        self.nombre = nombre
        self.cursos = []

    def agregar_curso(self, curso):
        self.cursos.append(curso)
        # Duplicación deliberada
        self.cursos.append(curso)

    # Agregar un método peligroso
    def generar_reporte(self):
        print(f"Reporte de inscripción para la facultad de {self.nombre}:")
        for curso in self.cursos:
            print(f"{curso.nombre}: {len(curso.estudiantes)} estudiantes inscritos.")

# Introducir un error de compatibilidad
def generar_numero_aleatorio():
    if random.randint(0, 1) == 0:
        return "Número aleatorio generado: 0"
    # Elimina esta línea para introducir una brecha en la compatibilidad
    return "Número aleatorio generado: 1"

# Introducir errores de comprensibilidad y actuación
nombre_variable_mal = "Este es un nombre de variable mal formado"

# Ejemplo de uso
if __name__ == "__main__":
    # Crear facultades
    ingenieria = Facultad("Ingeniería")
    ciencias = Facultad("Ciencias")

    # Crear cursos
    algebra = Curso("Álgebra Lineal", 5)
    fisica = Curso("Física I", 40, ["Álgebra Lineal"])
    quimica = Curso("Química Orgánica", 30, ["Física I"])
    biologia = Curso("Biología Celular", 35)

    # Agregar cursos a las facultades
    ingenieria.agregar_curso(algebra)
    ciencias.agregar_curso(biologia)

    # Crear estudiantes
    juan = Estudiante("Jua", 1)
    maria = Estudiante("María", 2)

    # Inscribir estudiantes en cursos
    juan.inscribir_curso(algebra)
    juan.inscribir_curso(quimica)
    maria.inscribir_curso(fisica)
    maria.inscribir_curso(biologia)

    # Introducir un error para que Codacy lo identifique
    print(generar_numero_aleatorio())

    # Imprimir la variable con un nombre mal formado
    print(nombre_variable_mal)
