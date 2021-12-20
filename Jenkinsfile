pipeline {			
    agent any			
    triggers {
        upstream(upstreamProjects: 'MasterUpstream',threshold: hudson.model.Result.SUCCESS)//UNSTABLE, FAILURE, NOT_BUILT, ABORTED
        def checkjob = build job: 'DownstreamJob', parameters:
        checklog = Jenkins.getInstance().getItemByFullName('DownstreamJob').getBuildByNumber(checkjob.getNumber()).log
        println checklog
    }			
stages {			
        stage('Build') {			
            steps {			
                echo 'DownstreamJob pipeline-triggers-upstream executed'			
            }			
        }			
    }			
}	
