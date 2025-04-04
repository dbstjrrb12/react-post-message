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

This project uses changesets to manage versioning and changelog generation. Here's how it works:

1. When you create a PR, you can comment `/changeset [type]` to create a changeset file

   - `type` can be `patch`, `minor`, or `major`
   - The changeset file will be created in the `.changeset` directory
   - The file will be named with the PR number and title (e.g., `pr-30.md`)

2. The changeset file will contain:

   - The version bump type
   - The PR title as the changelog entry
   - The changeset will be committed to your PR branch

3. When you merge the PR:

   - The changeset will be applied
   - The version will be bumped according to the type
   - A changelog entry will be generated

4. If you need to modify the changeset:
   - You can edit the `/changeset` comment
   - The changeset file will be updated automatically
   - The changes will be committed to your PR branch

## License

MIT
