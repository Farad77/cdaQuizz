# Correction du Questionnaire sur Git

## Questions à choix unique (en français)

1. Quelle commande Git est utilisée pour créer une nouvelle branche ?
   
   Réponse correcte : a) git branch new-branch
   
   Explication : La commande 'git branch' suivie du nom de la nouvelle branche est utilisée pour créer une nouvelle branche dans Git. Cependant, cette commande crée la branche mais ne bascule pas dessus. Pour créer une branche et basculer dessus immédiatement, on utiliserait 'git checkout -b new-branch'.

2. Quelle commande Git permet de voir l'historique des commits ?
   
   Réponse correcte : b) git log
   
   Explication : La commande 'git log' affiche l'historique des commits dans le dépôt Git actuel. Elle montre les détails de chaque commit, y compris l'identifiant SHA, l'auteur, la date et le message du commit.

## Questions ouvertes (en anglais)

1. Explain the difference between 'git merge' and 'git rebase'. When would you use one over the other?

   Réponse modèle : 
   'git merge' and 'git rebase' are both commands used to integrate changes from one branch into another, but they do so in different ways:

   - 'git merge' creates a new commit that combines the changes from the source branch into the target branch. It preserves the entire history of both branches.

   - 'git rebase' moves the entire feature branch to begin on the tip of the main branch, effectively incorporating all of the new commits in main. Rebasing re-writes the project history by creating brand new commits for each commit in the original branch.

   When to use merge:
   - When you want to preserve the entire history of your project
   - When working on a shared branch and want to maintain the context of the branch

   When to use rebase:
   - When you want to keep a linear project history
   - For cleaning up local changes before pushing to a shared repository
   - When working on a feature branch and want to incorporate the latest changes from the main branch

   In general, it's safer to use merge in public branches and rebase for cleaning up local branches before merging.

2. What is a "detached HEAD" state in Git and how can it occur?

   Réponse modèle:
   In Git, a "detached HEAD" state occurs when you checkout a specific commit, tag, or remote branch instead of a local branch. In this state, the HEAD (which usually points to the current branch) is "detached" from any branch and points directly to a commit.

   A detached HEAD can occur in several ways:
   1. Directly checking out a commit hash: `git checkout <commit-hash>`
   2. Checking out a tag: `git checkout <tag-name>`
   3. Checking out a remote branch without creating a local branch: `git checkout origin/branch-name`

   In a detached HEAD state, you can make changes and create commits, but these commits won't belong to any branch. If you switch to another branch without creating a new branch to save your work, these commits could be lost and later cleaned up by Git's garbage collection.

   To get out of a detached HEAD state, you can either:
   1. Create a new branch at your current position: `git checkout -b new-branch-name`
   2. Check out an existing branch: `git checkout existing-branch-name`

   The detached HEAD state can be useful for temporary inspection of old commits or tags, but it's important to be aware of its implications for your work.

