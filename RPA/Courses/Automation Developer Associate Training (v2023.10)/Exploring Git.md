## 🗺️Lesson overview

The objective of this Git lesson is to provide an overview of Git version control system and its basic concepts. By the end of this lesson, you should have a clear understanding of Git's purpose, benefits, and how to perform basic Git operations.

---

## 🌿About Git

- [[GIT]]
---

## Comparing SVN and Git Side-by-Side 

SVN (Subversion) and Git are both popular version control systems used in software development. While they serve similar purposes, they differ in their underlying architecture, workflow models, and features. Here's a comparison of SVN and Git:

| |SVN|GIT|
|---|---|---|
|**Architecture**|**SVN** is a centralized version control system, where a central repository stores the entire history and versions of files. Developers typically check out a working copy from the central repository, make changes, and commit them back.|**Git** is a distributed version control system, where each developer has a complete local copy of the repository. This allows developers to work independently and commit changes locally before synchronizing them with remote repositories.|
|**Branching and Merging**|**SVN** supports branching and merging, but it follows a copy-modify-merge approach. Each branch is essentially a copy of the trunk or another branch, and developers merge changes back to the main branch manually.|**Git** provides powerful branching and merging capabilities. Branches are lightweight and can be created and merged easily. Git allows for various branching strategies (such as feature branches, release branches, etc.) and provides efficient merging mechanisms.|
|**Performance**|**SVN** performs well for smaller repositories and projects with fewer files. However, as the repository size grows, SVN's centralized architecture can lead to slower operations, especially for tasks like history traversal.|**Git** is designed to handle large repositories efficiently, thanks to its distributed nature. Most operations are performed locally, making Git faster for common tasks such as committing, branching, merging, and switching between branches.|
|**Offline Work**|**SVN** requires a network connection to the central repository for most operations. Working offline is limited, as you need network access to commit changes or access the repository's full history.|**Git** enables full offline work since each developer has a complete local repository copy. Developers can commit changes and access the repository's history without network connectivity.|
|**Community and Ecosystem**|**SVN** has a mature user base and a well-established ecosystem. It has been around for a longer time, and there are many tools and integrations available for SVN.|**Git** has gained immense popularity and has a larger user community. It has a vast ecosystem with a wide range of tools, services, and integrations built around it.|