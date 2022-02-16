# LearningGit

## Features

### Feature: Learning Basic Git Scenarios

> \#level \#basic

```yaml
Scenario: You have decided in your team to develop a new application. You need to create a collaboration within your team so your colleagues can participate improving the application.
 Given: there is no collaborative environment to develop an app
  When: you create a git repository in GitHub named “LoremIpsum”
   And: give enough 'access rights' to the team members
  Then: “LoremIpsum” repository will be available for collaboration 
   And: the team members can reach the repository

#TIP: N/A
```


```yaml
Scenario: You have created a repository in GitHub but you have realised that the displayed name of the remote repository is wrong.
 Given: There is a GitHub repository named ”LoremIpsum”
  When: You change the name of the display name of the repository to “LearningGit”.
  Then: Your colleagues can see the display name of “LoremIpsum” repository as “LearningGit” 
   And: The URL of the repository will be the same as ”LoremIpsum”

#TIP: change .git/description
```
	
```yaml
Scenario: You have created a repository in GitHub but you have realised that the name of the remote repository is wrong.
 Given: There is a GitHub repository named “LoremIpsum” 
  And : the display name as “LearningGit”
  When: you change the name of the name of the repository to “LearningGit”
  Then: the URL of the repository will change to ”LearningGit”
   And: the connection between local git and remote git will be broken
   And: git push command will not be working as expected anymore

#TIP: Go to github website settings
```

```yaml
Scenario: You have changed the name of the remote repository and the your local git is not working any more.
 Given: There is a GitHub repository named ”LearningGit” 
  And : Your local git configuration is still looking at the old repository URL “LoremIpsum” 
  When: You call the “git remote set-url” command
  Then: The connection between local git and remote git will be established again.
   And: git push command will be working as expected anymore

#TIP: Remote set-url
```

```yaml
Scenario: You have created a new file in your local computer and you would like to share this file with you colleagues. What would you do?
 Given: There is a GitHub repository named “LearningGit” 
  And : main branch exist
  And : There is a new file named “newfile.md” that contains at line 1 “newfile is created” on your local git
  When: You call the “git add, git commit and push” commands on main branch
  Then: The newfile.md will be in repository on main branch.

#TIP: Push
```
