# 🚀 Getting Started with Trapies (Strapi)

Trapies is a powerful CMS built with Strapi, allowing you to manage and distribute content with ease. Follow this guide to set up and run your project.

## 📌 Prerequisites

Before getting started, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (Recommended: LTS version)
- [Yarn](https://yarnpkg.com/) or npm
- [PostgreSQL](https://www.postgresql.org/) (if not installed, follow the setup instructions below)

## 🫠 Installation

Clone the repository and navigate into the project directory:

```sh
git clone https://github.com/your-repo/trapies.git
cd trapies
```

Install dependencies:

```sh
yarn install
# or
npm install
```

## 🔧 PostgreSQL Configuration

Trapies uses PostgreSQL as the database. If PostgreSQL is not installed, follow these steps:

### Installing PostgreSQL

#### On macOS (Using Homebrew):
```sh
brew install postgresql
brew services start postgresql
```

#### On Ubuntu/Debian:
```sh
sudo apt update
sudo apt install postgresql postgresql-contrib
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

#### On Windows:
Download and install PostgreSQL from [official site](https://www.postgresql.org/download/windows/).

### Creating a Database
After installation, create a new database for Trapies:
```sh
psql -U postgres
CREATE DATABASE trapies_db;
CREATE USER trapies_user WITH ENCRYPTED PASSWORD 'your_password';
ALTER ROLE trapies_user SET client_encoding TO 'utf8';
ALTER ROLE trapies_user SET default_transaction_isolation TO 'read committed';
ALTER ROLE trapies_user SET timezone TO 'UTC';
GRANT ALL PRIVILEGES ON DATABASE trapies_db TO trapies_user;
```

### Configure Database Connection in Strapi
Edit `config/database.js` or `.env` file:
```env
DATABASE_CLIENT=postgres
DATABASE_HOST=127.0.0.1
DATABASE_PORT=5432
DATABASE_NAME=trapies_db
DATABASE_USERNAME=trapies_user
DATABASE_PASSWORD=your_password
DATABASE_SSL=false
```

## 🚀 Running the Application

### `develop`
Start the Strapi application with autoReload enabled:
```sh
yarn develop
# or
npm run develop
```

### `start`
Run the Strapi application in production mode:
```sh
yarn start
# or
npm run start
```

### `build`
Build the Strapi admin panel:
```sh
yarn build
# or
npm run build
```

## ⚙️ Deployment

Strapi provides various deployment options, including [Strapi Cloud](https://cloud.strapi.io). Check out the [deployment documentation](https://docs.strapi.io/dev-docs/deployment) for more details.

```sh
yarn strapi deploy
```

## 📚 Learn More
- [Strapi Documentation](https://docs.strapi.io) - Official Strapi docs
- [Strapi Tutorials](https://strapi.io/tutorials) - Guides and tutorials
- [Strapi Blog](https://strapi.io/blog) - Latest updates and articles
- [GitHub Repository](https://github.com/strapi/strapi) - Contribute to Strapi

## ✨ Community
- [Discord](https://discord.strapi.io) - Join the Strapi community
- [Forum](https://forum.strapi.io/) - Ask questions and get answers
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of useful Strapi resources

---

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>

