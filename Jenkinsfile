

@Library('pipeline-library-demo')_

def test(String abc){
    echo "Hello, ${abc}."
}

node('maven-label'){
    
    stage("prep"){
       git 'https://github.com/devops-apr/xcard.git' 
    }
    stage("shredlib"){
        sayHello "Ravi"
    }
     stage("custom"){
        test "Devops"
    }
   
    stage("download"){
        download_artifact "http://"
    }
}
