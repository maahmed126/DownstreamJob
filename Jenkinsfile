pipeline {			
    agent any			
    triggers {
        upstream(upstreamProjects: 'MasterUpstream',threshold: hudson.model.Result.SUCCESS)//UNSTABLE, FAILURE, NOT_BUILT, ABORTED
        def checkjob = build job: 'DownstreamJob', parameters: [ any params here]
        checklog = Jenkins.getInstance().getItemByFullName('job name').getBuildByNumber(checkjob.getNumber()).log
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
