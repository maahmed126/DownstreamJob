pipeline {			
    agent any			
    triggers {
        upstream(upstreamProjects: 'MasterUpstream',threshold: hudson.model.Result.SUCCESS)//UNSTABLE, FAILURE, NOT_BUILT, ABORTED
    }
         upstreamBuilds = manager.build.getUpstreamBuilds();
        upstreamJob = upstreamBuilds.keySet().iterator().next();
        lastUpstreamBuild = upstreamJob.getLastBuild();
        if(lastUpstreamBuild.getResult().isBetterThan(manager.build.result)) {
        lastUpstreamBuild.setResult(manager.build.result);
}              
stages {			
        stage('Build') {			
            steps {			
                echo 'DownstreamJob pipeline-triggers-upstream executed'
            }			
        }			
    }			
}	
