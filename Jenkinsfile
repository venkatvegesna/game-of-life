  
node('slave-01'){
    stage('scm'){
        git 'https://github.com/wakaleo/game-of-life.git'
    }

    stage('build'){
        sh label: '', script: 'mvn clean package'

    }

    stage('postbuild'){
        junit 'gameoflife-web/target/surefire-reports/*.xml'
        archiveArtifacts 'gameoflife-web/target/*.war'
        
    }

}