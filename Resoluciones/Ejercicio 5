import java.text.SimpleDateFormat
/*
EJERCICIO 5
Integrar Github con Jenkins:
Desde Github desarrollar un Jenkinsfile que cuente con 2 stages:
- Stage Calcular Edad:  En base a una fecha de nacimiento informada como variable Global se debe calcular la edad de la misma, utilizando la función getYear(), donde se debe restar el año de la fecha informada al año actual (que también debe estar almacenado en una variable) 
- Stage Generar Txt:
Generar un fichero de salida con la información calculada.
En Github se debe crear una rama que se llame “desarrollo” donde este alojado el Jenkinsfile que contenga el código a ejecutar.

Entregables:
-	Link del repositorio de Github con el Jenkinsfile
*/
def fecha_nacimiento = '04/06/1992'
def anio_fecha_actual = new Date().getYear().toInteger()
//def fecha_nacimiento_anio = fecha_nacimiento.getYear()

pipeline
{
    agent any
    
    stages
    {
        stage("Calcular edad")
        {
            steps
            {
                script
                {
                    def fecha = new SimpleDateFormat("dd/MM/yyyy").parse(fecha_nacimiento)
                    edad = anio_fecha_actual - fecha.getYear().toInteger()
                    string_edad = "La edad es: "+edad
                }
            }
            
        }
        
        stage("Imprimo la informacion")
        {
            steps
            {
            script
            {
            writeFile(file: "salida.txt", text: string_edad)
            echo "El archivo fue generado."
            }
            }
        }
    }
    
}
