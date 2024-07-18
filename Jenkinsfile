pipeline {
    agent any

    parameters{ 

        string(name:'Env',defaultValue:'Test',description:'version to deploy')
        booleanParam(name:'executeTests',defaultValue: true,description:'decide to run tc')
        choice(name:'APPVERSION',choices:['1.1','1.2','1.3'])
    
    }

    stages {
        stage('compile') {
            steps {
                echo "Compiling the codes in ${params.Env}"
            }
        }
        stage('UnitTest') {
            when{
                expression{
                    params.executeTests= true
                }
            }
            steps {
                echo 'Test the code'
            }
        }
        stage('package') {
            steps {
                echo "Package the code ${params.APPVERSION}"
            }
        }
    }
}
