pipeline {			
    agent any			
    triggers {
        upstream(upstreamProjects: 'MasterUpstream',threshold: hudson.model.Result.SUCCESS)//UNSTABLE, FAILURE, NOT_BUILT, ABORTED
    }			
stages {			
        stage('Build') {			
            steps {			
                echo 'DownstreamJob pipeline-triggers-upstream executed'
                upstreamBuilds = manager.build.getUpstreamBuilds();
                upstreamJob = upstreamBuilds.keySet().iterator().next();
                lastUpstreamBuild = upstreamJob.getLastBuild();
                if(lastUpstreamBuild.getResult().isBetterThan(manager.build.result)) {
               lastUpstreamBuild.setResult(manager.build.result);
}              

            }			
        }			
    }			
}	
