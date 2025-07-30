Push Notifier 📧
A simple GitHub Action workflow that sends an email notification on every push to the main branch. This is a learning project to understand repository automation and CI/CD basics.

🚀 What It Does
This project uses a GitHub Actions workflow to automatically send an email to a specified recipient whenever new code is pushed. This is useful for keeping track of updates on a personal project or notifying team members of changes.

The email notification includes:

The name of the repository.

The username of the person who pushed the changes.

The commit message.

A direct link to view the commit on GitHub.

⚙️ How It Works
The automation is defined entirely within the .github/workflows/email-notify.yml file.

Trigger: The workflow is triggered by a push event on the main branch.

Job: A single job runs on a GitHub-hosted virtual machine (ubuntu-latest).

Steps:

It first checks out the repository's code to access commit details.

It then uses the popular dawidd6/action-send-mail action from the GitHub Marketplace to send the email via a Gmail SMTP server.

Credentials (email address and password) are stored securely using GitHub's encrypted secrets.

🛠️ How to Use This in Your Own Repository
Copy the Workflow File: Copy the .github/workflows/email-notify.yml file into the same directory in your own repository.

Update the Recipient: Change the to: email address inside the file to your own.

Add Secrets: In your repository's Settings > Secrets and variables > Actions, add the following two secrets:

MAIL_USERNAME: Your full Gmail address.

MAIL_PASSWORD: A 16-character Google App Password for the Mail app