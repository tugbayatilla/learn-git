# LearningGit

## Features

### Feature: Learning Basic Git Scenarios

> \#level \#basic

```yaml
Scenario: Initialisation - You have decided in your team to develop a new application. You need to create a collaboration within your team so your colleagues can participate improving the application.
Given: there is no collaborative environment to develop an app
When: you create a git repository in GitHub named “LoremIpsum”
   And: give enough 'access rights' to the team members
Then: “LoremIpsum” repository will be available for collaboration 
   And: the team members can reach the repository

#TIP: N/A
```

```yaml
Scenario: Changing repository display name - You have created a repository in GitHub but you have realised that the displayed name of the remote repository is wrong.
Given: There is a GitHub repository named ”LoremIpsum”
When: You change the name of the display name of the repository to “LearningGit”.
Then: Your colleagues can see the display name of “LoremIpsum” repository as “LearningGit” 
   And: The URL of the repository will be the same as ”LoremIpsum”

#TIP: change .git/description
```
	
```yaml
Scenario: Changing repository name - You have created a repository in GitHub but you have realised that the name of the remote repository is wrong.
Given: There is a GitHub repository named “LoremIpsum” 
   And: the display name as “LearningGit”
When: you change the name of the name of the repository to “LearningGit”
Then: the URL of the repository will change to ”LearningGit”
   And: the connection between local git and remote git will be broken
   And: git push command will not be working as expected anymore

#TIP: Go to github website settings
```

```yaml
Scenario: Re-establish connection between local and remote git - You have changed the name of the remote repository and the your local git is not working any more.
Given: There is a GitHub repository named ”LearningGit” 
   And: Your local git configuration is still looking at the old repository URL “LoremIpsum” 
When: You call the “git remote set-url” command
Then: The connection between local git and remote git will be established again.
   And: git push command will be working as expected anymore

#TIP: Remote set-url
```

```yaml
Scenario: Sending assets to repository - You have created a new file in your local computer and you would like to share this file with you colleagues.
Given: There is a GitHub repository named “LearningGit” 
   And: main branch exist
   And: There is a new file named “newfile.md” that contains at line 1 “newfile is created” on your local git
When: You call the “git add, git commit and push” commands on main branch
Then: The newfile.md will be in repository on main branch.

#TIP: Push
```

```yaml
Scenario: Working in separate environment - The customer asks you to implement new feature to the application.
Given: There is a GitHub repository named “LearningGit” 
   And: main branch exist
   And: branch “feature/feature1” does not exist 
When: you create a new branch named “feature/feature1” from main branch
   And: switch to the branch “feature/feature1” branch with “git checkout” command
   And: create a new file named “feature1.md” contains “feature1 is implemented” at line 1
   And: you call the “git add, git commit and push with upstream flag” commands
Then: the new branch “feature/feature1” with newfile.md will be in repository.

#TIP: - Branch, Checkout, Push
```

```yaml
Scenario: Setting up test environment - The customer asks that they need a new environment to check the changes before going to production.
Given: There is a GitHub repository named “LearningGit” 
   And: main branch exist 
   And: branch “test” does not exist 
When: You create a new branch named “test” from main branch
   And: Switch to the branch “test” branch with “git checkout” command
   And: You call the “git push with upstream flag” commands 
Then: The new branch “test” will be in repository exactly the same as main branch.

#TIP: Branch, Checkout, Push
```

```yaml
Scenario: Resolve Conflicts - You are implementing a new feature to the application. You have finished your changes and pushed your code to the repository. !!Damn!!. Somebody else also has changed something before your changes.
Given: There is a GitHub repository named “LearningGit” 
   And: Branch “feature/feature1” exist
   And: You call “git checkout feature/feature1” command
   And: “feature1.md” at line 2 was added by somebody as “feature1 was changed by somebody.”
When: You have changed the same file “feature1.md” at line 2 as “feature1 was changed my me”
   And: You call the “git push” command
Then: Git will raise a merge conflict error message.

#TIP: Push
```

```yaml
Scenario: Resolve Conflicts 2 - You are implementing a new feature to the application. You have finished your changes and pushed your code to the repository. !!Damn!!. Somebody else also has changed something before your changes and your push is not working.
Given: There is a GitHub repository named “LearningGit” 
   And: Branch “feature/feature1” exist
   And: There is a merge conflict on file “feature1.md” at line 2.
When: You call “git merge main” command
   And: Resolve the conflicts
   And: Call the “git push” command
Then: Your changes will be in branch “feature/feature1”

#TIP: 
```

```yaml
Scenario: Changing the any/old commit message - You had created very ugly commit messages earlier and you would like to change this old commit messages.
Given: There is a GitHub repository named “LearningGit” 
   And: Branch “feature/feature1” exist
   And: There is a commit with “this is ugly message” message 3 commits earlier 
When: You call “git log” command to find the commit-id
   And: You call “git rebase -i feature/feature1 {commit-id}” command with interactive flag
   And: Change the commit message with using “reword” keyword 
   And: Call the “git push” command
Then: Your new commit message will be visible on remote branch “feature/feature1”

#TIP: 
```

```yaml
Scenario: Merge commits - You have created couple of commits and then you have realised that actually these commits should be only one.
Given: There is a GitHub repository named “LearningGit” 
   And: Branch “feature/feature1” exist
   And: There is a commit with “this is ugly message” message
When: You call “git log” command to find the commit-id
   And: You call “git rebase -i ...” command with interactive flag
   And: Change the commit message
Then: Your new commit message will be visible in branch “feature/feature1”

#TIP: Rebase
```

```yaml
Scenario: Sending any/old commit to main - You are developing a new feature, during the time in a certain state of your development, the customer asks you to send this state to the test system, but somehow you have forgot to send this state and continued developing more requirements to the feature, then you have realised that you should have sent it.
Given: There is a GitHub repository named “LearningGit” 
   And: Branch “feature/feature2” exist with multiple commits
   And: Branch “test” exist
   And: pushed a commit1 on branch "feature/feature2" with message "first commit"
   And: pushed an another commit2 with message "second commit"
When: you call 'git cherry-pick ...' command for commit1 to test branch 
Then: you can only see the commit1 on bracmch 'test'

#TIP: Cherry-pick
```


```yaml
Scenario: Using 3rd party code - You have decided to use some functionality from another project in your organisation or in GitHub.
Given: There is a GitHub repository named “LearningGit” 
   And: There is a GitHub repository named “AnotherRepo” with one file which is called 'another.md'
When: you call 'git submodule add {repo_url}' command
   And: call 'git submodule update ...' command
   And: 
   And: 
Then: you can see '.gitmodules' file in root directory
   And: you can reach the 'another.md' file

#TIP: submodules
```

```yaml
Scenario: Recovery - You have decided to delete the branch you are working on for a reason and then you have realised that it was a mistake. 
Given: 
   And: 
   And: 
When: 
   And: 
   And: 
   And: 
Then: 

#TIP: reflog, log, reset
```

