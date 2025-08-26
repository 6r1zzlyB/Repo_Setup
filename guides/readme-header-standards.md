# README Header Standards

This guide defines the standardized header format for all personal repositories. Since most repositories are private and intended for personal use, the standards emphasize confidentiality and personal development context.

## Standard Header Structure

### 1. Title
```markdown
# [Project Name]
```

**Guidelines:**
- Use clear, descriptive project names
- Avoid abbreviations unless widely understood
- Use title case for proper nouns
- Keep concise but descriptive

### 2. Badge Section

**Standard Badge Order:**
1. **License Badge** (Always first, always red for proprietary)
2. **Author Badge** (Blue, with email link)
3. **Status Badge** (Orange for private repositories, varies by project state)
4. **Technology/Platform Badge** (Blue, project-specific)
5. **Additional Badges** (Optional, project-specific)

```markdown
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](./LICENSE)
[![Author](https://img.shields.io/badge/Author-Matthew%20Stdenis-blue.svg)](mailto:matthew.h.stdenis@gmail.com)
[![Status](https://img.shields.io/badge/Status-Private%20Repository-orange.svg)](https://github.com/6r1zzlyB/[repository-name])
[![Technology](https://img.shields.io/badge/[Technology]-[Version]-blue.svg)]([link-to-technology-docs])
```

### 3. Description

**Format:**
- One-line description (concise summary, emphasizing personal use)
- Blank line
- Detailed description paragraph

```markdown
[One-line description of the project purpose and primary functionality for personal use]

[Detailed description paragraph explaining the project's purpose, capabilities, and personal development goals. Focus on learning objectives, personal workflow improvements, or specific problems being solved for personal use.]
```

### 4. Metadata Section

**Standard Format:**
```markdown
**Author:** Matthew Stdenis
**Created:** [Year]
**License:** All Rights Reserved (see [LICENSE](./LICENSE))

**IMPORTANT:** This repository is confidential and intended for personal use only. It is strictly forbidden to share any part of this repository with any third party without written consent from Matthew Stdenis.
```

**Optional additions:**
- **Last Updated:** [Date] (for frequently updated projects)
- **Version:** [Version] (for versioned projects)
- **Documentation Standards:** [Reference to style guide] (for complex projects)

## Badge Color Standards

### Status Badge Colors

- `orange` - Private Repository (most common for personal repos)
- `brightgreen` - Active Template, Production Ready
- `green` - Active Development, Personal Project
- `yellow` - Maintenance Mode, Learning Project
- `red` - Deprecated, Archived
- `blue` - Documentation, Reference Material

### Technology Badge Colors
- `blue` - Primary technology/platform
- `lightblue` - Secondary technology
- `success` - Best practices, standards
- `informational` - Documentation, guides

## Repository Type Variations

### 1. Personal Development Projects

```markdown
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](./LICENSE)
[![Author](https://img.shields.io/badge/Author-Matthew%20Stdenis-blue.svg)](mailto:matthew.h.stdenis@gmail.com)
[![Status](https://img.shields.io/badge/Status-Private%20Repository-orange.svg)](https://github.com/6r1zzlyB/[repo])
[![Technology](https://img.shields.io/badge/Node.js-20+-blue.svg)](https://nodejs.org/)
[![Version](https://img.shields.io/badge/Version-1.0.0-green.svg)](CHANGELOG.md)
```

### 2. Personal Script Collections

```markdown
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](./LICENSE)
[![Author](https://img.shields.io/badge/Author-Matthew%20Stdenis-blue.svg)](mailto:matthew.h.stdenis@gmail.com)
[![Status](https://img.shields.io/badge/Status-Private%20Repository-orange.svg)](https://github.com/6r1zzlyB/[repo])
[![Shell Script](https://img.shields.io/badge/Shell-Bash-green.svg)](https://www.gnu.org/software/bash/)
[![Platform](https://img.shields.io/badge/Platform-Linux-blue.svg)](https://www.linux.org/)
```

### 3. Personal Templates & Documentation

```markdown
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](./LICENSE)
[![Author](https://img.shields.io/badge/Author-Matthew%20Stdenis-blue.svg)](mailto:matthew.h.stdenis@gmail.com)
[![Status](https://img.shields.io/badge/Status-Active%20Template-brightgreen.svg)](https://github.com/6r1zzlyB/[repo])
[![Documentation](https://img.shields.io/badge/Documentation-Comprehensive-blue.svg)](https://github.com/6r1zzlyB/[repo])
[![GitHub Best Practices](https://img.shields.io/badge/GitHub-Best%20Practices-success.svg)](https://docs.github.com/en/contributing)
```

## Standard Notice Sections

### Confidentiality Notice (standard for all personal repositories)

```markdown
**IMPORTANT:** This repository is confidential and intended for personal use only. It is strictly forbidden to share any part of this repository with any third party without written consent from Matthew Stdenis.
```

### Additional Legal Notice (optional for particularly sensitive repositories)

```markdown
## 🚨 Additional Legal Notice

**This software contains proprietary methods and implementations.**

- **Personal Use Only**: This repository is intended solely for personal development and learning
- **No Distribution**: Copying, distributing, or creating derivative works is strictly prohibited
- **Confidential Information**: May contain sensitive personal data, API keys, or proprietary algorithms
- **Access Control**: Authorized personnel only - unauthorized access is prohibited

For any questions regarding usage or access, contact the repository owner directly.
```

## Implementation Checklist

- [ ] Title follows naming conventions
- [ ] Badges in correct order with proper colors
- [ ] License badge links to LICENSE file
- [ ] Author badge includes email link
- [ ] Status badge reflects current project state
- [ ] Technology badges are relevant and current
- [ ] One-line description is concise and clear
- [ ] Detailed description provides sufficient context
- [ ] Metadata section includes required fields
- [ ] Optional notices added if applicable
- [ ] All links are functional
- [ ] Formatting is consistent with standards

## Maintenance

- Review and update badges quarterly
- Update status badges when project state changes
- Keep technology version badges current
- Verify all links are functional
- Update metadata when significant changes occur

---

**Note:** This standard applies to all personal repositories. Consistency in header formatting improves professionalism and user experience across the entire GitHub organization.
