# php-nvm

🐳 **php-nvm** is a generic, lightweight Docker image for PHP applications that includes [NVM](https://github.com/nvm-sh/nvm), allowing dynamic management of multiple Node.js versions at runtime.

[![Docker Pulls](https://img.shields.io/docker/pulls/ycollective/php-nvm)](https://hub.docker.com/r/ycollective/php-nvm/)
![NVM Version](https://img.shields.io/badge/nvm-v0.40.5-blue)

---

## 🚀 Features

- ✅ PHP 8.x support (8.0–8.5)
- ✅ Multi-arch images for `linux/amd64` and `linux/arm64` (Apple Silicon / M1 compatible)
- ✅ Pre-installed [NVM](https://github.com/nvm-sh/nvm) for managing multiple Node.js versions
- ✅ Ideal for modern full-stack PHP projects that require Node.js tooling (e.g. Webpack, Vite, etc.)
- ✅ CI-friendly: small, clean, and consistently versioned
- ✅ Useful system tools: `git`, `rsync`, `openssh-client`, `make`, `curl`, etc.
- ✅ All images share the same consistent build logic

---

## 📦 Available Tags

| Tag  | PHP Version | Included Tools                         |
|------|-------------|----------------------------------------|
| 8.0  | 8.0         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.1  | 8.1         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.2  | 8.2         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.3  | 8.3         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.4  | 8.4         | ✅ PHP, Composer, NVM, Node.js via NVM |
| 8.5  | 8.5         | ✅ PHP, Composer, NVM, Node.js via NVM |

> ℹ️ Images include NVM (v0.40.5). The exact Node.js version is not preinstalled — use `nvm install` as needed in your Dockerfile or entrypoint script.

---

## 🧪 Usage

### 🐋 Example Dockerfile

```Dockerfile
FROM ycollective/php-nvm:8.3

# Install Node.js 18 using NVM
RUN source ~/.nvm/nvm.sh && \
    nvm install 18 && \
    nvm use 18 && \
    node -v && npm -v

# Set up your app
COPY . /app
WORKDIR /app
RUN composer install
```

### 💻 Run it interactively

```sh
docker run -it --rm ycollective/php-nvm:8.3 bash
```

## 🤝 Contributing

Any contributions are welcomed!

Use Conventional Commits with a required scope:

- ✅ feat(8.4): add PHP 8.4 support
- ✅ fix(8.3): correct NVM installation path

GitHub Actions will:

- ✅ Enforce PR title formatting
- ✅ Ensure the Docker image builds successfully

See [CONTRIBUTING.md](CONTRIBUTING.md) for full contribution guidelines.

---

Project: https://github.com/Y-collective/php-nvm

Huge thanks to [ocReaper](https://github.com/ocReaper) for the [original](https://github.com/ocReaper/php-nvm) idea, foundation, and code that made this project possible.
Your work gave this project its starting point, and we deeply appreciate the effort you put into it.
