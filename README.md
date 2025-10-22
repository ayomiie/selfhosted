##  Steps I Followed

1. Created a new GitHub repository named **selfhosted**.  
2. Went to **Settings → Actions → Runners → Add Runner** to get setup commands.  
3. Downloaded and configured the runner on my local PC (`C:\actions-runner`).  
4. Started the runner using PowerShell with `.\run.cmd`.  
5. Created a workflow file `.github/workflows/test-runner.yml` to run a test job.  
6. Adjusted PowerShell execution policies to allow the script to run successfully.  
7. Re-ran the workflow and confirmed the self-hosted runner executed the job locally.

Challenges & How I Solved Them

PowerShell blocked unsigned scripts which I Changed execution policy to **RemoteSigned** and used `ExecutionPolicy Bypass`. 
| Workflow failed due to syntax errors | Fixed YAML indentation and removed invalid emoji characters I used earlier.
| Runner didn’t start initially | Rechecked path, reconfigured token, and ran as admin to register correctly.


Security Considerations

Execution policy limited to **RemoteSigned** for safety.  
Avoided storing sensitive credentials in code or workflows.  
Limited runner permissions to the minimum required.  
Ensured runner only communicates with GitHub’s trusted endpoints.
