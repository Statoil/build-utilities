# build-utilities

## Utils
### Library Vulnerability
* /src/LibVulnerability
* Check-PackageVulnerability.ps1

This ps utility will try and locate NuGet packages from all projects in the solution (either current working directory or -SolutionFolder), and query for vulnerabilities in them.
Supports both project.json and packages.config.

The script uses ossindex rest API to query for vulnearbility.
Caching is implemented to support CI builds. Three conditions invalidate the cache:
* The database has been updated since last check
* New libraries are detected
* Different versions of an already checked library is detected

#### Improvements
* Final output report
* VSTS Build task
  * Log vulnerability events to an app insight component?
  * Webhook alerts?

* MSBuild task?

