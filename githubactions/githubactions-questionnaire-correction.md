# Correction du Questionnaire sur GitHub Actions

## Questions à choix unique (en français)

1. Où sont stockés les fichiers de workflow GitHub Actions dans un dépôt ?
   
   Réponse correcte : c) Dans le dossier .github/workflows
   
   Explication : Les fichiers de workflow GitHub Actions sont stockés dans le dossier `.github/workflows` à la racine du dépôt. C'est à cet endroit que GitHub recherche automatiquement les fichiers de workflow à exécuter.

2. Quel est le format de fichier utilisé pour définir les workflows GitHub Actions ?
   
   Réponse correcte : c) YAML
   
   Explication : Les workflows GitHub Actions sont définis dans des fichiers YAML. YAML est choisi pour sa lisibilité et sa facilité d'écriture, ce qui le rend idéal pour les fichiers de configuration.

## Questions ouvertes (en anglais)

1. Explain the difference between a job and a step in a GitHub Actions workflow. How are they related?

   Réponse modèle : 
   In a GitHub Actions workflow:

   Job:
   - A job is a set of steps that execute on the same runner.
   - Jobs can run independently of each other or sequentially if they depend on other jobs.
   - Each job runs in a fresh instance of the runner environment.

   Step:
   - A step is an individual task within a job.
   - Steps can run commands, run setup tasks, or run an action.
   - Steps within a job execute on the same runner, allowing them to share data.

   Relationship:
   - A job consists of one or more steps.
   - All steps in a job execute sequentially on the same runner.
   - If any step in a job fails, subsequent steps in the same job are usually skipped (unless configured otherwise).
   - Different jobs can run in parallel, but steps within a single job always run sequentially.

   This structure allows for complex workflows where different tasks (jobs) can run independently, while ensuring that closely related actions (steps) are executed in a controlled, sequential manner.

2. What are GitHub Secrets and why are they important in the context of GitHub Actions?

   Réponse modèle:
   GitHub Secrets are encrypted environment variables that you create in a repository or organization. They allow you to store sensitive information securely.

   Importance in GitHub Actions:

   1. Security: Secrets are encrypted and can only be accessed by GitHub Actions. They're never exposed in plain text in the Actions logs.

   2. Sensitive Data Protection: They're used to store sensitive data like API keys, access tokens, and passwords, which are often needed in CI/CD processes but shouldn't be exposed in your code.

   3. Environment Separation: Secrets allow you to keep your production credentials separate from your development environment.

   4. Access Control: Repository secrets are only accessible to users with admin access to the repository, adding an extra layer of security.

   5. Flexibility: You can use different secrets for different environments (e.g., staging vs production), making it easy to manage different configurations.

   6. Integration: Many third-party services and platforms can be easily integrated into your workflows using secrets to store authentication details.

   By using GitHub Secrets, you can ensure that your workflows have access to necessary credentials and sensitive information without compromising security. This is crucial for tasks like deploying to servers, accessing private APIs, or publishing packages.

