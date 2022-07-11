pipeline {
    agent any
    stages {
        stage('clonning git') {
            steps {
                checkout scm
            }
        }
        stage('Setup parameters') {
            steps {
                script { 
                    properties([
                        parameters([
                            choice(
                                choices: ['red', 'white', 'black','yellow'], 
                                name: 'your_fav_color'
                            ),
                            choice(
                                choices: ['jaipur', 'jodhpur', 'udaipur'],
                                name: 'your_fav_city'
                            ),
                            text(
                                defaultValue: '''
                                This is some of my fav choices,
                                ''', 
                                 name: 'description'
                            ),
                            string(
                                defaultValue: 'your name please', 
                                name: 'type_name', 
                                trim: true
                            )
                        ])
                    ])
                }
            }
        }
    }   
}
node{
    echo "${params.your_fav_color}"
    echo "${params.your_fav_city}"
    echo "${params.type_name}"
}
