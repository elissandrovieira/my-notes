## 🗺️overview

Storage Buckets provide a per-folder storage solution for developers to leverage in creating automation projects  

This lesson mainly deal with the use of Storage Buckets, more precisely how to create them in Orchestrator and then how to use them in automation projects built using UiPath Studio. A Storage Bucket is created within a folder, so you can control access to it and its contents with fine-grained permissions and role assignment models.

---

## 🤔What are Storage Buckets?

Storage Buckets are Orchestrator entities used for storing files which can be used in automation projects. UiPath Studio offers a set of activities to simplify working with Storage Buckets. These activities are available in the UiPath.System.Activities pack, under Orchestrator.

Storage Buckets can be created using the Orchestrator database or some external providers, such as Azure, Amazon, or MinIO. Each Storage Buckets is a folder-scoped entity, allowing fine-grained control over storage and content access.

---

## 🤔Why do you need Storage Buckets?

UiPath Studio offers many options to work with files in automation projects. In certain contexts, Storage Buckets may be the best way: for example, when you need to use large files stored in a centralized location or when you need to grant access to multiple robots in a controlled way.

---

## 🤔How to use Storage Bucket in Studio?

![[Pasted image 20250505001538.png]]
