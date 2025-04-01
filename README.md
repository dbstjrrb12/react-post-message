# React Post Message

A React hook for cross-window communication using `window.postMessage`.

## Features

- Type-safe message passing between windows
- Support for multiple target windows
- Automatic cleanup of event listeners
- TypeScript support
- Automated version management with changesets
  - Automatic version bumping based on PR comments
  - Support for patch, minor, and major version updates
  - Automated changelog generation
  - Changeset files are created in PR branches
  - Version updates are applied when PRs are merged
  - Changeset files are automatically created when you comment `/changeset [type]` on PRs
  - Changeset files are created in the PR branch and merged to main when PR is merged
  - Changeset files are created with PR number and title for better tracking
- Easy to use API!!

## Installation

```bash
npm install @yoonseokgyu/react-post-message
# or
yarn add @yoonseokgyu/react-post-message
# or
pnpm add @yoonseokgyu/react-post-message
```

## Usage

```tsx
import { usePostMessage } from '@yoonseokgyu/react-post-message';

function App() {
  const { postMessage } = usePostMessage({
    targetOrigin: 'https://example.com',
    targetWindow: window.open('https://example.com'),
  });

  const handleClick = () => {
    postMessage({
      type: 'GREETING',
      payload: 'Hello from parent window!',
    });
  };

  return <button onClick={handleClick}>Send Message</button>;
}
```

## License

MIT
