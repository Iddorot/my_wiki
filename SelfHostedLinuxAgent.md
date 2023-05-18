## Intro:
How to create a self-hosted Linux Agent for Azure Devops Pipelines - on Windows Machine.

1. [Self-hosted Windows agents:](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/v2-windows?view=azure-devops#authenticate-with-a-personal-access-token-pat)
    1. Authenticate with a personal access token (PAT) 
    2. Download and configure the agent
1. [Set Up python](https://stackoverflow.com/questions/60936103/install-python-to-self-hosted-windows-build-agent):
The Agent dir should looks like that, need to install python inside the x64 folder:
      
     ``` $AGENT_TOOLSDIRECTORY/
              Python/
                  3.7.9/
                      x64/
                          Doc/
                          Lib/
                          Scripts/
                          python.exe
                          ...etc...
                      x64.complete 
                      ```
1. [Install Bash On Windows](https://hackernoon.com/how-to-install-bash-on-windows-10-lqb73yj3)

    1. To enable virtualisation you must use one of the [VM Sizes](https://learn.microsoft.com/en-us/answers/questions/813416/how-do-i-know-what-size-azure-vm-supports-nested-v)
    2. [Change The agent task to run as the user that installed the Windows subsystem](https://stackoverflow.com/questions/73053374/bash-task-in-azure-devops-not-working-on-self-hosted-windows-agent)
