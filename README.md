# React Post Message

A React hook for cross-window communication using `window.postMessage`.

## Features

- Type-safe message passing between windows
- Support for multiple target windows
- Automatic cleanup of event listeners
- TypeScript support
- Automated version management with changesets
- Easy to use API

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
