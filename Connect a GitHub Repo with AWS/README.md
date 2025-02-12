# **Connect a GitHub Repo with AWS**

## **Objective**
This project demonstrates how to connect a local Git repository to GitHub for version control and collaboration. I set up a GitHub repository, pushed code changes, and authenticated using GitHub tokens for secure communication.

## **How Git and GitHub Were Used**
- **Version Control**: I used Git to track changes in my web app code and GitHub to host the repository remotely. This ensures version control and easy collaboration, allowing seamless synchronization between local and remote repositories.
- **Authentication**: I encountered GitHub's new token-based authentication system, which replaced the traditional password authentication for Git operations. I set up a personal access token (PAT) to authenticate and push my changes securely.

## **Git Workflow**
1. **Initialization**: Ran `git init` in the project folder to create a local Git repository.
2. **Commit Changes**: Used `git add .` to stage changes and `git commit -m "Message"` to record changes with a message describing the updates.
3. **Push Changes**: Ran `git push -u origin master` to push commits to the GitHub repository, setting the upstream branch for easy future pushes.

## **Challenges**
- **GitHub Token Authentication**: Initially, authentication failed because GitHub no longer supports password authentication for Git operations. I resolved this by generating a personal access token (PAT) through GitHub's "Developer settings."
- **Synchronization**: I didn't see my changes in GitHub until I committed and pushed them. Once pushed, my local changes were reflected in the remote repository.

## **GitHub Tokens**
GitHub tokens are used for secure access to repositories. I created a new token from the "Personal Access Tokens" section under "Developer settings" on GitHub. This token was used for authentication in place of my password.

## **Project Time**
This project took approximately **2 hours**. It involved setting up Git, configuring the local repository, making changes, and securely authenticating with GitHub.

## **Conclusion**
This project helped me understand the process of connecting a local Git repository to GitHub, using version control for managing changes, and handling authentication with GitHub tokens. The experience improved my knowledge of Git operations and best practices for code management.

