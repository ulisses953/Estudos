Erro : `Error: JavaFX runtime components are missing, and are required to run this application`

Para resolver esse erro se deve clicar em **run** e depois  **addConfig** e depois colar o exemplo a seguir 
```JSON
{

    // Use IntelliSense to learn about possible attributes.

    // Hover to view descriptions of existing attributes.

    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387

    "version": "0.2.0",

    "configurations": [

        {

            "type": "java",

            "name": "Current File",

            "request": "launch",

            "mainClass": "${file}"

        },

        {

            "type": "java",

            "name": "App",

            "request": "launch",

            "mainClass": "App",

            "projectName": "java-database_8caecb59",

            "vmArgs": "--module-path \"C:/Program Files (x86)/Java/javafx-sdk-21.0.1/lib\" --add-modules javafx.controls,javafx.fxml"

        }

    ]

}
```