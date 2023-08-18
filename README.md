# helloworld.py

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Python Script') {
            steps {
                sh 'python helloworld.py'
            }
        }
    }
}



Started by user Yosef Gessese
java.io.IOException: error=2, No such file or directory
	at java.base/java.lang.ProcessImpl.forkAndExec(Native Method)
	at java.base/java.lang.ProcessImpl.<init>(ProcessImpl.java:314)
	at java.base/java.lang.ProcessImpl.start(ProcessImpl.java:244)
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1110)
Caused: java.io.IOException: Cannot run program "git" (in directory "/var/lib/jenkins/caches/git-0ec28be8790ee9aa72bf724fc8e3ec79"): error=2, No such file or directory
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1143)
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1073)
	at hudson.Proc$LocalProc.<init>(Proc.java:254)
	at hudson.Proc$LocalProc.<init>(Proc.java:223)
	at hudson.Launcher$LocalLauncher.launch(Launcher.java:997)
	at hudson.Launcher$ProcStarter.start(Launcher.java:509)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2835)
Caused: hudson.plugins.git.GitException: Error performing git command: git init /var/lib/jenkins/caches/git-0ec28be8790ee9aa72bf724fc8e3ec79
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2858)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2762)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2757)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommand(CliGitAPIImpl.java:2051)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl$5.execute(CliGitAPIImpl.java:1071)
Caused: hudson.plugins.git.GitException: Could not init /var/lib/jenkins/caches/git-0ec28be8790ee9aa72bf724fc8e3ec79
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl$5.execute(CliGitAPIImpl.java:1073)
	at org.jenkinsci.plugins.gitclient.CliGitAPIImpl.init(CliGitAPIImpl.java:360)
	at hudson.plugins.git.GitAPI.init(GitAPI.java:244)
	at jenkins.plugins.git.GitSCMFileSystem$BuilderImpl.build(GitSCMFileSystem.java:388)
	at jenkins.scm.api.SCMFileSystem.of(SCMFileSystem.java:219)
	at org.jenkinsci.plugins.workflow.cps.CpsScmFlowDefinition.create(CpsScmFlowDefinition.java:118)
	at org.jenkinsci.plugins.workflow.cps.CpsScmFlowDefinition.create(CpsScmFlowDefinition.java:70)
	at org.jenkinsci.plugins.workflow.job.WorkflowRun.run(WorkflowRun.java:312)
	at hudson.model.ResourceController.execute(ResourceController.java:101)
	at hudson.model.Executor.run(Executor.java:442)
Finished: FAILURE
