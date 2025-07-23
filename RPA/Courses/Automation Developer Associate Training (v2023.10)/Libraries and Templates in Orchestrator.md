## 🗺️Overview

Orchestrator can also be used to store libraries and templates so that they can be used again and again for  reusability among other features that include automation and robot management. Orchestrator is a tool that all developers within a company can use to share development assets and make sure the right versions are being used.

---

## 📚Libraries
### What is a Library?

Libraries in UiPath encapsulate reusable components, such as login workflows or data processing logic, and are published as **NuGet packages**. Once stored in **Orchestrator**, these libraries can be shared across teams and automation projects to ensure consistency and efficiency.

### Creating Libraries

There are two ways to create a library in UiPath Studio:

- **From scratch** via the "Library" project type.
- **Extracting from an existing process**, turning selected workflows into a reusable library.

Regardless of the method, the goal is to modularize common automation components to avoid redundancy.

### Customizing Library Activities

Each library activity can expose **arguments** as **custom properties**. These can be configured with:

- **Tooltips** for usability
- **Required flags** to enforce input  
    This enhances clarity and control when other developers use the library.

### Publishing to Orchestrator

Before publishing:

- Confirm the **library feed settings** in Orchestrator (Host, Tenant, or both)
- Choose the **deployment type** and security options
- Set a **clear versioning strategy** and release notes

Publishing is done via UiPath Studio, pushing the library package to the Orchestrator feed for reuse.

### Installing & Using Libraries in Projects

Libraries can be added as dependencies in:

- Regular UiPath projects
- **Project templates**, making them available by default in newly created projects

Once installed, the activities become accessible in the Activities panel and behave like any built-in activity.

### Managing Credentials in Reusable Components

When using libraries that require credentials:

- Prefer **Orchestrator Assets**, like credential assets
- Use built-in activities like **Get Credential** to retrieve them securely  
    This approach avoids hardcoding and keeps libraries environment-independent.

### Updating Libraries

Updates to libraries are versioned and managed within Orchestrator:

- New versions can be published from Studio with a changelog
- Existing projects will show an **update notification** if a newer version is available
- Updating is seamless and helps maintain a single source of truth across automations

---

## 📑Templates

Templates allow automation teams to:

- Start projects with predefined structure and dependencies
- Include custom libraries by default
- Store templates locally, in Orchestrator, or across networked feeds

Combining templates and libraries supports **modular development, faster onboarding**, and **code reuse** at scale.