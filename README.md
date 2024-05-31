# On The Pulse Consultancy - Website

Welcome to the repository for On The Pulse static website. This README provides information about the project, its structure, and how to work with the codebase.

## Technologies Used

- HTML5
- TailwindCSS

## Local Development

Being a static website, the codebase can be run locally by opening the `public/index.html` file in a browser.

## System Architecture

The website is deployed on AWS S3 and CloudFront. The stack can be found in [deploy/static-website-final.yaml](./deploy/static-website-final.yaml).

## Deployment

Visit [docs/DEPLOYMENT.md](./docs/DEPLOYMENT.md).

## CI/CD

- The CI/CD pipeline is managed by GitHub Actions.
- For authentication, the IAM user `StaticWebsiteDeployUser` has been created with permission to asume the role that has the necessary permissions. The access key and secret key of this user are stored in GitHub Secrets.
- The workflow can be found in [.github/workflows/main.yaml](./.github/workflows/main.yaml).

## Contact

For any inquiries, please contact [José Arévalo] at <jose.matias.arevalo@gmail.com>.
