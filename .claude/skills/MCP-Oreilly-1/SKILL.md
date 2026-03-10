# MCP-Oreilly-1 Development Patterns

> Auto-generated skill from repository analysis

## Overview

This repository demonstrates Model Context Protocol (MCP) server implementations across multiple programming languages. It showcases a multi-language approach to building MCP tools and services, with implementations in TypeScript/Node.js, Python, and Java. The codebase emphasizes modular architecture with language-specific directories and consistent configuration patterns.

## Coding Conventions

### File Naming
- Use **camelCase** for all file names
- Main server files typically named `index.ts`, `server.py`, or similar language conventions
- Configuration files follow standard conventions (`package.json`, `tsconfig.json`, `pyproject.toml`)

### Import/Export Style
```typescript
// Use relative imports
import { someFunction } from './utils';
import { MCPServer } from '../server';

// Use named exports
export { MyClass, myFunction };
export const config = { ... };
```

### Directory Structure
```
/language-name/
  ├── src/
  │   ├── index.ts (or main entry point)
  │   └── [feature-files]
  ├── package.json (or equivalent)
  └── [language-specific config]
```

## Workflows

### Create New Language Implementation
**Trigger:** When someone wants to add support for a new programming language to the MCP server collection
**Command:** `/new-language-impl`

1. Create a new directory with the language name
2. Upload core implementation files:
   - Main server file (`index.ts`, `server.py`, `Main.java`)
   - Package configuration (`package.json`, `pyproject.toml`, `pom.xml`)
3. Add language-specific configuration files:
   - TypeScript: `tsconfig.json`
   - Python: `pyproject.toml`, `__init__.py`
   - Java: `pom.xml`
4. Organize source code in appropriate subdirectories (`src/`, etc.)
5. Update root documentation to reference new implementation

**Example TypeScript structure:**
```
/typescript/
  ├── src/
  │   └── index.ts
  ├── package.json
  └── tsconfig.json
```

### File Upload and Reorganization
**Trigger:** When someone uploads files in bulk and needs to organize them into proper directory structure
**Command:** `/upload-and-organize`

1. Upload all necessary files to the repository root
2. Create appropriate language/feature directories
3. Move files from root to their target locations:
   - `package.json` → `/language-dir/package.json`
   - Source files → `/language-dir/src/`
   - Config files → `/language-dir/[config-file]`
4. Verify all files are in correct locations
5. Clean up any remaining files in root directory

### Documentation Iteration
**Trigger:** When someone is creating or substantially updating project documentation
**Command:** `/update-docs`

1. Create initial `README.md` with basic project structure
2. Add overview of MCP server implementations
3. Document each language implementation with:
   - Setup instructions
   - Dependencies
   - Usage examples
4. Include architecture explanations
5. Add troubleshooting section
6. Iterate rapidly based on feedback, making multiple sequential commits

**Example README structure:**
```markdown
# MCP Server Implementations

## Overview
Multi-language implementations of MCP servers...

## Languages Supported
- [TypeScript/Node.js](./typescript/)
- [Python](./python/)
- [Java](./java/)

## Getting Started
[Setup instructions]
```

### Create New MCP Tool
**Trigger:** When someone wants to create a new MCP tool or service implementation
**Command:** `/new-mcp-tool`

1. Create tool-specific directory (e.g., `/weather-tool/`, `/sysinfo-tool/`)
2. Set up TypeScript configuration:
   ```json
   // package.json
   {
     "name": "mcp-tool-name",
     "main": "dist/index.js",
     "dependencies": {
       "@modelcontextprotocol/sdk": "^0.4.0"
     }
   }
   ```
3. Create main implementation file:
   ```typescript
   // src/index.ts
   import { Server } from '@modelcontextprotocol/sdk/server/index.js';
   
   const server = new Server({
     name: 'tool-name',
     version: '1.0.0'
   });
   ```
4. Add TypeScript configuration (`tsconfig.json`)
5. Implement tool-specific functionality
6. Test and document the new tool

## Testing Patterns

Tests follow the pattern `*.test.*` for test files. While specific testing framework is not detected, the convention suggests:

```typescript
// example.test.ts
describe('MCP Tool Tests', () => {
  test('should handle requests correctly', () => {
    // Test implementation
  });
});
```

## Commands

| Command | Purpose |
|---------|---------|
| `/new-language-impl` | Create a new MCP server implementation in a different programming language |
| `/upload-and-organize` | Upload files in bulk and reorganize into proper directory structure |
| `/update-docs` | Create or iteratively improve project documentation |
| `/new-mcp-tool` | Create a new MCP tool/service with complete TypeScript setup |