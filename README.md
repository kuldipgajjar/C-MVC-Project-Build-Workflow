# C-MVC-Project-Build-Workflow
This GitHub Actions workflow automates the build and deployment process for a C# MVC project. It performs the following steps:

1. **Build Projects**: Builds the C# MVC project using MSBuild for both the Web and API components.
2. **Create Directories**: Creates directories for the Web and API artifacts.
3. **Remove XML Files**: Deletes XML files from the API and Web directories to prepare for artifact copying.
4. **Copy Artifacts**: Copies the built artifacts to the respective directories for Web and API.
5. **Upload Artifacts**: Uploads the Web and API artifacts as GitHub Action artifacts.
6. **Download Artifacts**: Downloads the uploaded artifacts for verification or further processing.

7. ## Usage

8. ### Workflow Trigger

9. This workflow is triggered manually using the `workflow_dispatch` event.

10. ### Prerequisites

11. Ensure that the following tools are available on the runner:

    - Microsoft Visual Studio 2022 (or compatible version)
    - PowerShell for executing scripts

12. ### Workflow Steps

    1. **Checkout Repository**: Checks out the repository to the GitHub Actions runner.
    2. **Build Projects**: Uses MSBuild to build the Web and API projects.
    3. **Create API and Web Directories**: Creates directories for storing the built artifacts.
    4. **Delete XML Files**: Removes XML files from the API and Web directories.
    5. **Copy Artifacts**: Copies the built artifacts to the appropriate directories.
    6. **Upload Artifacts**: Uploads the artifacts as GitHub Action artifacts for later use.
    7. **Download Artifacts**: Downloads the uploaded artifacts to the runner for verification.
    8. **Check Artifacts**: Verifies the presence of artifacts in the downloaded directories.

13. ### Customize Paths

14. If your project's file structure differs, make sure to update the paths in the workflow script accordingly. Modify the following paths in the script to match your project structure:

  - `${{github.workspace}}\Web.csproj`
  - `${{github.workspace}}\API.csproj`
  - `${{github.workspace}}\Web`
  - `${{github.workspace}}\API`
  - `${{github.workspace}}\Web-artifacts`
  - `${{github.workspace}}\API-artifacts`

15. ### Notes

  - Ensure that appropriate permissions are set for executing scripts and creating directories.
  - Review the script and adjust any specific build configurations or additional steps as needed for your project.

16. ## License

17. This project is licensed under the [MIT License](LICENSE).
