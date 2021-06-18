def var=[
    a: 'hello',
    b: ['hello','git']
]

def var2=var.b ?: ''

pipeline {
    agent any
    
    stages {
        /*stage('test') {
            steps {
                script {
                    var.b.each {
                    sh "echo haelo"
                    }
                    
                }
            }
        } */       
        stage('test') {
            steps {
                script {
                    if (var2 != '') {
                        var.b.each {
                            sh "echo ${it}"
                            build job: "$it" //, wait: true
                        }
                    }    
                }
            }
        }   
    }
    
}
