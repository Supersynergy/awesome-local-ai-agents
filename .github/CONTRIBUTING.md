# Contributing to Awesome Local AI Agents

First off, thank you for considering contributing to this project! It's people like you that make this resource valuable for the entire community.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Submission Guidelines](#submission-guidelines)
- [Style Guide](#style-guide)
- [Quality Standards](#quality-standards)
- [Pull Request Process](#pull-request-process)

---

## Code of Conduct

By participating in this project, you agree to abide by our Code of Conduct:

- **Be respectful**: Treat everyone with respect and kindness
- **Be constructive**: Provide helpful feedback and suggestions
- **Be inclusive**: Welcome contributors of all backgrounds
- **Be patient**: Remember that maintainers are volunteers

---

## How Can I Contribute?

### Adding a New Framework or Tool

If you know of a local AI agent framework or LLM tool that should be included:

1. Ensure it meets our [quality standards](#quality-standards)
2. Follow the [submission guidelines](#submission-guidelines)
3. Add it to the appropriate file

### Improving Documentation

- Fix typos or grammatical errors
- Clarify confusing sections
- Add missing information
- Update outdated content

### Reporting Issues

- Report broken links
- Flag outdated information
- Suggest improvements
- Request new categories

### Sharing Use Cases

- Add real-world examples
- Share integration patterns
- Document best practices

---

## Submission Guidelines

### For Frameworks

When adding a new agent framework, include:

```markdown
### Framework Name

**Short description of what it does**

- **GitHub**: [owner/repo](https://github.com/owner/repo)
- **Stars**: X,XXX+
- **Language**: Python/JavaScript/etc.
- **License**: MIT/Apache-2.0/etc.

#### Overview

2-3 sentences describing the framework's purpose and approach.

#### Key Features

- Feature 1 - Brief description
- Feature 2 - Brief description
- Feature 3 - Brief description
- Feature 4 - Brief description

#### Best For

- Use case 1
- Use case 2
- Use case 3

#### Installation

\```bash
pip install framework-name
\```

#### Example

\```python
# Minimal working example
from framework import Agent

agent = Agent()
result = agent.run("task")
\```

#### Limitations

- Limitation 1
- Limitation 2
```

### For Local LLM Tools

When adding a new tool:

```markdown
### Tool Name

**The tagline or description**

- **Website**: [domain.com](https://domain.com)
- **GitHub**: [owner/repo](https://github.com/owner/repo) (if open source)
- **License**: License type
- **Platforms**: macOS, Windows, Linux

#### Overview

2-3 sentences about what the tool does and who it's for.

#### Key Features

- Feature 1
- Feature 2
- Feature 3

#### Strengths

- Strength 1
- Strength 2
- Strength 3

#### Limitations

- Limitation 1
- Limitation 2

#### Installation

Step-by-step installation instructions or commands.
```

### For Awesome Lists

```markdown
| [List Name](https://github.com/owner/repo) | X,XXX+ | Brief description |
```

### For Learning Resources

```markdown
| [Resource Name](https://url.com) | Provider | Focus Area | Free/Paid |
```

---

## Style Guide

### Markdown Formatting

- Use ATX-style headers (`#`, `##`, `###`)
- Include a blank line before and after headers
- Use fenced code blocks with language identifiers
- Use tables for structured comparisons
- Use bullet points for lists

### Writing Style

- Use clear, concise language
- Write in present tense
- Use active voice when possible
- Avoid jargon without explanation
- Be objective and factual

### Links

- Use descriptive link text
- Link to official sources when possible
- Verify all links work before submitting
- Use HTTPS links when available

### Code Examples

- Keep examples minimal but complete
- Include necessary imports
- Add comments for clarity
- Ensure code actually runs

---

## Quality Standards

### For Frameworks and Tools

To be included, a framework or tool must:

1. **Be relevant**: Focus on local AI agents or LLM deployment
2. **Be active**: Updated within the last 12 months
3. **Be documented**: Have basic documentation
4. **Be accessible**: Be available for public use
5. **Support local deployment**: Work without cloud services
6. **Have community**: At least 500 GitHub stars or significant usage

### For Resources

Learning resources must:

1. Be publicly accessible
2. Be relevant to local AI agents
3. Be up-to-date (within 2 years)
4. Provide value to the community

### What We Don't Include

- Paid-only products without free tier
- Abandoned projects (no updates in 2+ years)
- Cloud-only services
- Spam or low-quality content
- Duplicate entries

---

## Pull Request Process

### Before Submitting

1. **Search existing PRs**: Make sure it hasn't been proposed
2. **Check the list**: Ensure it's not already included
3. **Test your additions**: Verify links work
4. **Follow the style guide**: Match existing formatting

### Submitting Your PR

1. **Fork the repository**
2. **Create a branch**: `git checkout -b add-framework-name`
3. **Make your changes**: Follow the guidelines
4. **Commit**: Use clear commit messages
5. **Push**: `git push origin add-framework-name`
6. **Open PR**: Use the template below

### PR Template

```markdown
## Description

Brief description of what you're adding/changing.

## Type of Change

- [ ] Adding new framework/tool
- [ ] Adding new resource
- [ ] Fixing error/typo
- [ ] Improving documentation
- [ ] Other (describe)

## Checklist

- [ ] I've read the CONTRIBUTING.md
- [ ] Links are working
- [ ] Formatting matches existing content
- [ ] Information is accurate
- [ ] Meets quality standards

## Additional Notes

Any additional context or information.
```

### Review Process

1. Maintainers will review your PR
2. They may request changes or clarification
3. Once approved, your PR will be merged
4. You'll be credited in the commit history

### Timeline

- We aim to review PRs within 7 days
- Simple fixes are often merged quickly
- Larger additions may need discussion

---

## Recognition

All contributors are valued members of our community. Significant contributors may be:

- Listed in the README acknowledgments
- Invited to become maintainers
- Credited in release notes

---

## Questions?

If you have questions about contributing:

1. Check existing issues for answers
2. Open a new issue with the "question" label
3. Join our community discussions

---

## License

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

---

Thank you for helping make this resource better for everyone! Your contributions help developers around the world build better local AI agents.
