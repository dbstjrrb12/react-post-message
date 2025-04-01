# react-post-message

A React hook for cross-window communication using the `postMessage` API.

## Features

- Type-safe message handling
- Support for multiple windows
- Easy to use API
- Built with TypeScript
- Comprehensive documentation
- Automated version management

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
  const { sendMessage, receiveMessage } = usePostMessage({
    targetOrigin: 'https://example.com',
    onMessage: (event) => {
      console.log('Received message:', event.data);
    },
  });

  const handleClick = () => {
    sendMessage({ type: 'hello', data: 'world' });
  };

  return <button onClick={handleClick}>Send Message</button>;
}
```

## API

### usePostMessage

A hook that provides methods for sending and receiving messages between windows.

```tsx
const { sendMessage, receiveMessage } = usePostMessage({
  targetOrigin: string;
  onMessage?: (event: MessageEvent) => void;
});
```

#### Parameters

- `targetOrigin`: The origin of the target window. This is used to validate the origin of incoming messages.
- `onMessage`: A callback function that is called when a message is received.

#### Returns

- `sendMessage`: A function that sends a message to the target window.
- `receiveMessage`: A function that sets up a listener for incoming messages.

## License

MIT
