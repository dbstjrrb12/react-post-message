# React Post Message

A React hook for type-safe postMessage communication between windows.

## Features

- Type-safe message passing between windows
- Support for multiple target windows
- Automatic cleanup of event listeners
- TypeScript support
- Automated version management with changesets
  - Automatic version bumping based on PR comments
  - Support for patch, minor, and major version updates
  - Automated changelog generation
  - Changeset files created in PR branches
  - Version updates applied upon PR merges
  - Changeset files created when commenting `/changeset [type]` on PRs
  - Changeset files named with PR number and title for better tracking
- Easy to use API

## Installation

```bash
pnpm add react-post-message
```

## Usage

```tsx
import { usePostMessage } from 'react-post-message';

function App() {
  const { postMessage } = usePostMessage();

  const handleClick = () => {
    postMessage('child', {
      type: 'GREET',
      payload: { name: 'John' },
    });
  };

  return <button onClick={handleClick}>Send Message</button>;
}
```

## Changeset Workflow

This project uses Changesets for version management. Here's how it works:

1. When you create a PR that changes packages, the workflow will automatically detect the changes and ask you to select a version bump type.
2. You can respond with one of these comments:
   - `/changeset major` - For breaking changes
   - `/changeset minor` - For new features
   - `/changeset patch` - For bug fixes
3. The workflow will create or update a changeset file with your selected version type and PR title.
4. When the PR is merged, the changeset will be included in the next release.

### Writing Changelog Entries

When creating a changeset, you can include additional information after the version type:

```
/changeset patch This fixes a critical bug in the message handling
```

This will be included in the changelog entry for better context.

## License

MIT
