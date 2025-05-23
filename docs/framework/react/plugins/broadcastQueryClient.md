---
id: broadcastQueryClient
title: broadcastQueryClient (Experimental)
---

> VERY IMPORTANT: This utility is currently in an experimental stage. This means that breaking changes will happen in minor AND patch releases. Use at your own risk. If you choose to rely on this in production in an experimental stage, please lock your version to a patch-level version to avoid unexpected breakages.

`broadcastQueryClient` is a utility for broadcasting and syncing the state of your queryClient between browser tabs/windows with the same origin.

## Installation

This utility comes as a separate package and is available under the `'@tanstack/query-broadcast-client-experimental'` import.

## Usage

Import the `broadcastQueryClient` function, and pass it your `QueryClient` instance, and optionally, set a `broadcastChannel`.

```tsx
import { broadcastQueryClient } from '@tanstack/query-broadcast-client-experimental'

const queryClient = new QueryClient()

broadcastQueryClient({
  queryClient,
  broadcastChannel: 'my-app',
})
```

## API

### `broadcastQueryClient`

Pass this function a `QueryClient` instance and optionally, a `broadcastChannel`.

```tsx
broadcastQueryClient({ queryClient, broadcastChannel })
```

### `Options`

An object of options:

```tsx
interface BroadcastQueryClientOptions {
  /** The QueryClient to sync */
  queryClient: QueryClient
  /** This is the unique channel name that will be used
   * to communicate between tabs and windows */
  broadcastChannel?: string
  /** Options for the BroadcastChannel API */
  options?: BroadcastChannelOptions
}
```

The default options are:

```tsx
{
  broadcastChannel = 'tanstack-query',
}
```
