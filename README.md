# AI-Powered D365 F&O Code Review Workspace

A comprehensive workspace for conducting Microsoft Dynamics 365 Finance & Operations (D365 F&O) architecture reviews and code analysis using Azure DevOps integration and AI-powered code review capabilities.

## 🎯 Overview

This workspace provides a structured environment for D365 F&O developers and architects to perform thorough code reviews, architectural analysis, and compliance validation against Microsoft best practices. It integrates with Azure DevOps to streamline the review process and leverage AI assistance for comprehensive analysis.

## 🚀 Features

- **AI-Powered Code Reviews**: Leverages GitHub Copilot with specialized D365 F&O expertise
- **Azure DevOps Integration**: Direct integration with Azure DevOps for build analysis and changeset reviews
- **Architecture Compliance**: Automated checks against D365 F&O best practices and patterns
- **Security Analysis**: Comprehensive security review capabilities for X++ code
- **Performance Assessment**: Tools for analyzing performance implications of code changes

## 📋 Prerequisites

Before using this workspace, ensure you have:

- **Visual Studio Code** with the following extensions:
  - GitHub Copilot
  - Model Context Protocol (MCP) support
- **Azure DevOps Access**: Valid personal access token with appropriate permissions
- **Python 3.13+** for running the Azure DevOps tools
- **uvx** package manager for Python tools

## 🛠️ Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd d365-fo-code-reviews
```

### 2. Configure Environment Variables

Copy the example environment file and configure your Azure DevOps settings:

```bash
cp .env.example .env
```

Edit the `.env` file with your Azure DevOps configuration:

```bash
DEVOPS_ORGANIZATION=your_organization
DEVOPS_PROJECT=your_project
DEVOPS_PAT=your_personal_access_token
```

### 3. Install Dependencies

The workspace uses `uvx` to manage Python dependencies. The Azure DevOps tools will be automatically installed when first used.

### 4. Configure VS Code

The workspace is pre-configured with Model Context Protocol (MCP) settings. Ensure GitHub Copilot is installed and authenticated.

## 🔍 Usage


### Getting an Azure DevOps Personal Access Token (PAT)

Before using this workspace, you'll need to create a Personal Access Token to authenticate with Azure DevOps:

#### Step-by-Step Guide

1. **Navigate to Azure DevOps**
    - Go to [dev.azure.com](https://dev.azure.com)
    - Sign in with your Microsoft account or organizational account

2. **Access User Settings**
    - Click on your profile picture in the top-right corner
    - Select **Personal access tokens** from the dropdown menu

3. **Create New Token**
    - Click **+ New Token**
    - Provide a descriptive name (e.g., "D365 F&O Code Review Workspace")
    - Set expiration period (recommended: 90 days or as per your organization's policy)

4. **Configure Token Permissions**
    Select the following scopes for full workspace functionality:
    - **Build**: Read & execute
    - **Code**: Read
    - **Project and Team**: Read
    - **Release**: Read
    - **Work Items**: Read

    > **Note**: Use minimal required permissions based on your review needs. For read-only operations, avoid granting write permissions.

5. **Generate and Copy Token**
    - Click **Create**
    - **Important**: Copy the token immediately and store it securely
    - You won't be able to see it again after leaving this page

6. **Store Token Securely**
    - Add the token to your `.env` file as `DEVOPS_PAT=your_token_here`
    - Never commit this token to version control
    - Consider using a password manager for secure storage

#### Security Best Practices

- **Rotation**: Rotate tokens every 90 days or as per your organization's policy
- **Minimal Scope**: Only grant permissions necessary for your review tasks
- **Monitoring**: Regularly review token usage in Azure DevOps settings
- **Revocation**: Immediately revoke tokens if compromised or no longer needed

#### Troubleshooting

If you encounter authentication issues:
- Verify the token hasn't expired
- Check that your organization allows personal access tokens
- Ensure the token has the required scopes for your operations
- Contact your Azure DevOps administrator if organizational policies restrict PAT creation


### Fork this repository

To get started with your own copy of the D365 F&O Code Review Workspace:

1. **Navigate to the repository**: Go to the GitHub repository page for this workspace
2. **Click Fork**: Use the "Fork" button in the top-right corner of the repository
3. **Choose destination**: Select your GitHub account or organization as the destination
4. **Make repository private**: During the fork process, ensure you check the option to make the repository private to protect your Azure DevOps configuration and any sensitive project information
5. **Clone your fork**: Clone your forked repository to your local machine:
    ```bash
    git clone https://github.com/YOUR_USERNAME/d365-fo-code-reviews.git
    cd d365-fo-code-reviews
    ```
6. **Configure upstream**: Add the original repository as upstream for future updates:
    ```bash
    git remote add upstream https://github.com/ORIGINAL_OWNER/d365-fo-code-reviews.git
    ```
7. **Verify setup**: Check your remote repositories:
    ```bash
    git remote -v
    ```

8. Configure Environment Variables

Copy the example environment file and configure your Azure DevOps settings:

```bash
cp .env.example .env
```

Edit the `.env` file with your Azure DevOps configuration:

```bash
DEVOPS_ORGANIZATION=your_organization
DEVOPS_PROJECT=your_project
DEVOPS_PAT=your_personal_access_token
```

> **Important**: Make sure to keep your forked repository private to protect your Azure DevOps configuration, personal access tokens, and any organization-specific code review processes.

This ensures you have your own private copy to customize while maintaining the ability to pull updates from the original repository.


### Using GitHub Copilot in Agent Mode

This workspace is designed to work with GitHub Copilot in agent mode. Use natural language prompts to interact with your Azure DevOps environment and conduct code reviews. Here are some example prompts you can use:

#### Azure DevOps Operations
- **"Review changeset 17"** - Analyze a specific changeset for code quality, patterns, and compliance
- **"Compare changeset 18 and 19"** - Compare two changesets to understand differences and impact
- **"Check build status"** - Get an overview of recent build statuses and pipeline health
- **"Explain failed build tasks"** - Analyze failed builds and identify root causes

#### Code Review Prompts
- **"Analyze this X++ class for performance issues"** - Review code for performance anti-patterns
- **"Check security implementation in this form"** - Validate security patterns and role-based access
- **"Review data entity design"** - Examine data entities for best practices and OData compliance
- **"Validate extension patterns"** - Ensure proper extension usage over overlayering

### Azure DevOps Integration

Access Azure DevOps data directly from VS Code using Copilot prompts:

- **Build Analysis**: Review build logs and identify failures
- **Changeset Review**: Analyze code changes and their impact
- **Pipeline Monitoring**: Track build pipelines and their status
- **Historical Analysis**: Compare changes across multiple changesets

### Architecture Review Process

Follow the structured review process defined in the Copilot instructions:

1. **Code Quality Assessment**
   - X++ language standards validation
   - AOT structure review
   - Performance pattern analysis

2. **Security Review**
   - Role-based access control validation
   - Data protection compliance
   - Security implementation patterns

3. **Integration Analysis**
   - API design review
   - Data entity validation
   - External system integration patterns

## 📁 Workspace Structure

```
d365-fo-code-reviews/
├── .env.example              # Environment configuration template
├── .gitignore               # Git ignore patterns
├── .vscode/
│   └── mcp.json            # Model Context Protocol configuration
├── .github/
│   └── copilot-instructions.md  # Specialized D365 F&O review guidelines
└── README.md               # This file
```

## 🔧 Configuration

### Model Context Protocol (MCP)

The workspace uses MCP to integrate Azure DevOps tools. The Azure DevOps MCP server is provided by [azuredevops-tools](https://github.com/mafzaal/azuredevops-tools). Configuration is in `.vscode/mcp.json`:

```json
{
    "servers": {
        "azuredevops-tools": {
            "type": "stdio",
            "command": "uvx",
            "args": [
                "--directory",
                "${workspaceFolder}",
                "azuredevops-tools"
            ],
            "envFile": "${workspaceFolder}/.env"
        }
    }
}
```

### Copilot Instructions

The specialized D365 F&O review guidelines are defined in `.github/copilot-instructions.md`, covering:

- Code quality standards
- Architecture patterns
- Security requirements
- Performance guidelines
- Integration best practices

## 📊 Review Categories

The workspace supports structured reviews across multiple categories:

### 🔴 Critical Issues
- Security vulnerabilities
- Performance bottlenecks
- Compliance violations
- Data integrity risks

### 🟡 Important Issues
- Best practice violations
- Maintainability concerns
- Architecture deviations
- Code quality issues

### 🟢 Suggestions
- Optimization opportunities
- Code improvements
- Alternative patterns
- Enhancement recommendations

### 📚 Educational
- Learning opportunities
- Best practice explanations
- Pattern demonstrations
- Framework usage examples

## 🎯 Review Focus Areas

### Application Lifecycle Management (ALM)
- Solution packaging strategies
- Version control practices
- CI/CD pipeline configurations
- Environment promotion processes

### Data Management
- Data entity design and performance
- Integration patterns
- Data security implementations
- Upgrade and migration strategies

### Performance & Scalability
- Batch processing optimization
- Caching strategies
- Database query performance
- Resource management

### Security Architecture
- Role-based security validation
- Record-level security (RLS)
- Audit trail implementation
- Compliance features

## 🛡️ Security Considerations

- Never commit actual personal access tokens to version control
- Use environment variables for sensitive configuration
- Regularly rotate Azure DevOps personal access tokens
- Follow principle of least privilege for DevOps permissions

## 🤝 Contributing

To contribute to this workspace:

1. Fork the repository
2. Create a feature branch
3. Make your changes following D365 F&O standards
4. Submit a pull request with detailed description

## 📚 Resources

### Microsoft Documentation
- [D365 F&O Developer Documentation](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/dev-tools/developer-home-page)
- [X++ Language Reference](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-language-reference)
- [Application Lifecycle Management](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs)

### Best Practices
- [Performance Guidelines](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/dev-tools/developer-home-page#performance)
- [Security Best Practices](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/sysadmin/security-architecture)

## 📄 License

This workspace configuration is provided as-is for educational and professional use in D365 F&O development environments.

## 🔗 Support

For issues or questions regarding this workspace:

1. Check the existing documentation
2. Review the Copilot instructions for guidance
3. Consult Microsoft's official D365 F&O documentation
4. Create an issue in the repository for workspace-specific problems

---

**Note**: This workspace is designed to enhance D365 F&O code review processes and should be used in conjunction with standard development practices and Microsoft guidelines.
