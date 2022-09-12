# Pipeline_Script

1, install Jenkin,

2, create a new item as a pipeline,

3, click "Advanced" to select "Git",

4, select "Pipeline script from SCM",

5, import repositroy from "https://github.com/pythonlhugithub/simplilearn-github.git" as https://github.com/pythonlhugithub/simplilearn-githubd.git,

6, click Save and Build this pipeline now,

7, check the stage view. build is done

8, success example:

<table><tr><td>
Started by user david lizhong huang
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin
[Pipeline] {
[Pipeline] stage
[Pipeline] { (check-out)
[Pipeline] git
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/pythonlhugithub/simplilearn-githubd.git
 > git.exe init C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin # timeout=10
Fetching upstream changes from https://github.com/pythonlhugithub/simplilearn-githubd.git
 > git.exe --version # timeout=10
 > git --version # 'git version 2.32.0.windows.2'
 > git.exe fetch --tags --force --progress -- https://github.com/pythonlhugithub/simplilearn-githubd.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe config remote.origin.url https://github.com/pythonlhugithub/simplilearn-githubd.git # timeout=10
 > git.exe config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git.exe rev-parse "refs/remotes/origin/master^{commit}" # timeout=10
Checking out Revision b7467b2c751e5bff9b96e56b200af5706dc27892 (refs/remotes/origin/master)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f b7467b2c751e5bff9b96e56b200af5706dc27892 # timeout=10
 > git.exe branch -a -v --no-abbrev # timeout=10
 > git.exe checkout -b master b7467b2c751e5bff9b96e56b200af5706dc27892 # timeout=10
Commit message: "Update README.md"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (build)
[Pipeline] echo
build-git-checkout
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>Build.bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>echo "Building the Project : Mon 12/09/2022 : 11:03:54.53" 
"Building the Project : Mon 12/09/2022 : 11:03:54.53"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (unit test)
[Pipeline] echo
unittest-git-checkout
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>Unit.bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>echo "Running Unit Test Cases : Mon 12/09/2022 : 11:03:54.88" 
"Running Unit Test Cases : Mon 12/09/2022 : 11:03:54.88"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (quality gate)
[Pipeline] echo
quality-git-checkout
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>Quality.bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>echo "Quality Gate Check : Mon 12/09/2022 : 11:03:55.25" 
"Quality Gate Check : Mon 12/09/2022 : 11:03:55.25"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (deploy)
[Pipeline] echo
deploy-git-checkout
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>Deploy.bat

C:\ProgramData\Jenkins\.jenkins\workspace\gitscriptinjenkin>echo "Deploying Build : Mon 12/09/2022 : 11:03:55.63" 
"Deploying Build : Mon 12/09/2022 : 11:03:55.63"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] echo
success
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
</td></tr></table>

9, Use Agent

9.1 label BUild-In Node as "windownode"

9.2 create a new item called agentjob and select "pipeline"

9.3 change agent any to agent 'windownode' in pipeline script

9.4 click build now to check  the stages view, it is successful

<table><tr><td>
 Started by user david lizhong huang
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\buildagentjob
[Pipeline] { (hide)
[Pipeline] stage
[Pipeline] { (check-out)
[Pipeline] git
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/pythonlhugithub/simplilearn-githubd.git
 
 </td></tr>
 <tr><td>
  two agents run at the same time
  
  Started by user david lizhong huang
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\buildagentjob
[Pipeline] {
[Pipeline] stage
[Pipeline] { (local agent to test)
[Pipeline] node
Running on Jenkins in C:\ProgramData\Jenkins\.jenkins\workspace\buildagentjob@2
[Pipeline] {
[Pipeline] echo
local agent is running
  </td></tr>
</table>
