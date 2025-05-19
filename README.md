# Angular Micro Frontends with Nx and Module Federation

This repository demonstrates how to implement **Micro Frontends** using **Angular**, **Nx**, and **Webpack Module Federation**. It follows the official Nx tutorial: [Dynamic Module Federation with Angular](https://nx.dev/recipes/angular/dynamic-module-federation-with-angular).

## 🧭 Overview

Micro Frontends is an architectural style where a frontend app is decomposed into individual, semi-independent "micro-apps" working loosely together. This approach promotes scalability, independent deployments, and better team autonomy.

This project uses **Nx**, a powerful monorepo tool for Angular, and sets up dynamic module federation using Webpack 5 to load Angular applications at runtime.

## 🏗️ What’s Included

- `host`: Shell application that dynamically loads remote apps. Here host is [dashboard]
- `remote1`, `remote2`, etc.: Independent Angular apps that are federated as remotes. here remote is [login]
- `libs/shared/...`: Shared libraries for code reuse (e.g., UI components, services, data access).
- Nx workspace structure with full integration support.

## 📦 Technologies Used

- [Nx](https://nx.dev) Monorepo
- [Angular](https://angular.io/)
- [Webpack Module Federation](https://webpack.js.org/concepts/module-federation/)
- [TypeScript](https://www.typescriptlang.org/)

## 🚀 Getting Started

### 1. Install dependencies

```bash
npm install
````

### 2. Serve the host and remotes

In separate terminals, run:

```bash
nx serve host
nx serve remote1
# Add more if needed: nx serve remote2
```

The host will be available at `http://localhost:4200/`, and it will dynamically load the remote apps when navigated to.

### 3. Generate shared services or components

Use Nx generators to create reusable logic:

```bash
nx g @nx/angular:service user --project=shared-data-access-user
```

Or components:

```bash
nx g @nx/angular:component header --project=shared-ui
```

## 🧩 Folder Structure

```
apps/
  host/
  remote1/
libs/
  shared/
    data-access-user/
    ui/
```

## 📚 Tutorial Reference

This implementation is based on the official Nx guide:
👉 [Dynamic Module Federation with Angular](https://nx.dev/recipes/angular/dynamic-module-federation-with-angular)

## ✅ Benefits of This Setup

* **Independent deployment** of remote apps
* **Code reuse** via shared libraries
* **Faster builds** with Nx caching and task orchestration
* **Scalable architecture** for teams and projects

---

## 🛠 Nx Commands Reference

* List all projects: `nx show projects`
* Run app: `nx serve <project-name>`
* Build app: `nx build <project-name>`
* Run tests: `nx test <project-name>`

---

## 📎 License

MIT
