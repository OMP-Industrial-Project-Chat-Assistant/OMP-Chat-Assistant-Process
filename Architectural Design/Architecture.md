# Introduction

**Version:** 1.0

**Last Edit:** 13.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Yaroslav Kim

**Approval Status:** N/A

**Type:** Architecture

**Description:** Description of current state of architecture.

**Dependencies:**
- [Business Context](</Context and Requirements Management/EN/Context/Business Context.md>)
- [Requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Justifications:
- This architecture allows for easy disribution of labor between developers, helping satisfy [Maintainability](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md#22-maintainability>)
- This specific architecture is the only known way of satisfying the functional requirements of the project.

# Content
## Current Data Flow
**Version**: 1.0

**Last Updated**: 16.03.2025


The following is the data flow for normal function: user asks question, and receives answer. The user does not interact with the system directly, but uses an external service.
![img](<../Diagrams/DataFlow.drawio.png>)
## Current System-Context Diagram
**Version**: 1.0

**Last Updated**: 16.03.2025
![img](<../Diagrams/SystemView.drawio.png>)
## Current Container Diagram
**Version**: 1.0

**Last Updated**: 16.03.2025
![img](<../Diagrams/ContainerView.drawio.png>)
## Current Components Diagram
**Version**: 1.0

**Last Updated**: 16.03.2025
![img](<../Diagrams/ComponentsView.drawio.png>)

# Changelog
- v1.0 - 13.04.2025. Conversion to new format. Yaroslav Kim