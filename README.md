# Your Portfolio Starter

A custom workshop starter for building a professional portfolio with Astro, Git, GitHub, VS Code, and Copilot.

## 1. Make it yours

Open `src/data/profile.js`. Change your name, role, introduction, skills, education, experience, project examples, links, and contact email.

Choose a visual style by changing `theme` to one of these values:

- `editorial` — warm, expressive, story-led
- `developer` — dark, technical, projects-first
- `professional` — structured and recruiter-friendly

The starter contains fictional example data. Replace it with accurate details about your own work. You do not need to include private information.

## 2. Preview locally

Requirements: Node.js 22, Git, and VS Code.

```bash
npm install
npm run dev
```

Open the local address printed in the terminal, usually `http://localhost:4321`. Keep the terminal running while you preview.

## 3. Connect to your own GitHub repository

Create an empty repository on GitHub, then run these commands in the VS Code terminal from this folder. Replace the uppercase placeholders with your GitHub username and repository name.

```bash
git init
git add .
git commit -m "Create my portfolio"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

## 4. Publish the site

1. In the repository, open **Settings → Pages**.
2. Set the source to **GitHub Actions**.
3. Open the **Actions** tab and watch **Build and deploy portfolio**.
4. After the run succeeds, open the published URL and test the links.

Astro configures the repository path automatically during the GitHub Actions build.

## Before you share

- Check the page on desktop and mobile.
- Use links that belong to you and point to the intended project.
- Do not publish passwords, API tokens, private keys, home addresses, or other information you want to keep private.
- Review AI-generated code before committing it.
- Describe your contribution honestly, including when a project was completed as part of a team.
