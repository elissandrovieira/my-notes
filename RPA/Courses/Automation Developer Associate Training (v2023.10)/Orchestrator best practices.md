## 🤔What you'll learn in this lesson

At the end of this lesson you should be able to:

1. Understand the best practices of working with Orchestrator Resources

## 👍A few best practices includes:

1. To reduce SQL Server allocation contention in a highly concurrent environment, make sure you employ an optimal number of tempdb data files that have equal sizing.

2. To mitigate the risks and potential impact from a malicious user, follow these guidelines:
    
    - Limit robot permissions to the minimum required to execute the particular automation(s).
    - In modern folders, disable robot creation for those users with administrator or other high-privilege roles in Orchestrator.
    
3. To mitigate the risks and potential impact from a malicious developer, follow these guidelines:
    
    - Maintain control and validation over any packages being deployed in Orchestrator.
    - Limit robot permissions to the minimum required to execute the particular automation(s).
    - In modern folders, disable robot creation for those users with administrator or other high-privilege roles in Orchestrator.
    
4. Change the default system administrator password (that was communicated to you by our team). You can do this by editing the user profile information.

5. When you first log in to Orchestrator, do not select the Remember Me password. This helps you log out of the current session every time.

6. While enforcing an HTTPS connection is important, it is just as important to have an SSL certificate from a trusted provider.

7. It is recommended to add security caching directives to hide sensitive information that may be displayed in HTTP headers.

8. Do not use the Orchestrator installation root directory or any directory that gets served by a web server

9. Make sure the supplied folder or network share does not have any subdirectories or files containing sensitive information that should not be accessible to Orchestrator users or automations

10. Do not use a full partition, such as C:\, as it might result in read access to unexpected data

11. When possible, restrict the access to a subdirectory created specifically for storage buckets. For example, if you use C:\my_data to store all your data, you could create a subdirectory called storage_buckets, and then add C:\my_data\storage_buckets to the allowlist instead of C:\my_data

12. Look for hidden files and folders before deciding on the allowed paths as they might contain sensitive data

13. Use a specific folder in a network share instead of the whole network share (e.g. \\server.corp\sharedfolder)

14. Do not allow system-specific folders, such as C:\Windows, C:\Program Files or C:\ProgramData, as they might contain sensitive information

15. By default, the Elasticsearch security features are disabled if you have a basic or trial license. We strongly recommend that you enable them.