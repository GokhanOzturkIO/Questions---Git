## 1) What is Git?

Git is the most widely used version control system in the world. It is a free and open-source distributed version control system that records changes made to code over time in a special database called a repository. Git allows users to track project history, see who made changes and when, and revert the project to an earlier state if necessary. It is popular due to its speed, scalability, and efficient handling of branching and merging operations. Git enables developers to collaborate on projects, with each team member having a copy of the project with its history on their machine, allowing for local saving of project snapshots and synchronization with others even if the central server is offline.

---

## 2) What is the difference between "git pull" and "git fetch" commands?

`git fetch` downloads new data from a remote repository without integrating it into your working files, allowing you to review the changes before integrating them into your local repository.

`git pull`, on the other hand, downloads new data and directly integrates it into your current working copy files, which can be faster but also introduces changes and conflicts into your local repository.

`git fetch` is safer as it only downloads new data, while `git pull` integrates it into your current working copy files, which can cause conflicts and changes that require manual resolution.

---