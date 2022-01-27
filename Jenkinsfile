// Sintaxis declarativa: MAS SENCILLA y LA MAS USADA. Menos potente que la de scripting... 
//          pero mucho MAS que los proyectos de estilo libre
// Sintaxis de scripting: MAS COMPLEJA Y MAS POTENTE: Puedo hacer lo que quiera con Jenkins

pipeline {
    
    agent any // Para definir DONDE QUIERO QUE SE EJECUTE ESTA TAREA
    
    stages {
       stage("Etapa 1") {
           steps { // Hacemos las llamadas a los plugins
               sh "echo Soy la etapa 1" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Sigo" // Llamada al plugin que ejecuta una shell
               sh "echo Salgo de la etapa 1" // Llamada al plugin que ejecuta una shell
           }
           post {
               always { // Post tareas que siempre deben de ejecutarse
                  sh "echo Acabó la etapa 1"
               }
               success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
                  sh "echo Y acabó bien"
               }
               failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
                  sh "echo Pero acabó mal"
               }
           }
       }
       stage("Etapa 2") {
           steps {
               sh """
               echo Soy la etapa 2
               echo Acabo la etapa 2
               """
           }
           post {
               always { // Post tareas que siempre deben de ejecutarse
                  sh "echo Acabó la etapa 2"
               }
               success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
                  sh "echo Y acabó bien"
               }
               failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
                  sh "echo Pero acabó mal"
               }
           }
       }
    }

    post {
       always { // Post tareas que siempre deben de ejecutarse
          sh "echo Acabó la etapa 2"
       }
       success { // Postareas que SOLO se ejecutan si los pasos (STEPS) han ido bien
          sh "echo Y acabó bien"
       }
       failure { // Postareas que SOLO se ejecutan si los pasos (STEPS) han dado error
          sh "echo Pero acabó mal"
       }
    }
}