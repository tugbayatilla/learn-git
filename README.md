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
	
