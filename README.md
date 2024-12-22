# Clipgen

A web clip and adhoc config generator.

## Installation

```bash
$ yarn add clipgen
```

## Usage

For webclips:

```ts
import { Config } from 'clipgen';

const config = await Config.render({
	type: 'web',
	name: "UseCodify's Site",
	author: 'UseCodify',
	desc: 'A test webclip',
	clips: [
		{
			name: 'UseCodify',
			url: 'https://UseCodify.Com',
		},
	],
	signing: {
		// Optional, only available using Node.js
		cert: '-----BEGIN CERTIFICATE-----\n...\n-----END CERTIFICATE-----',
		key: '-----BEGIN RSA PRIVATE KEY-----\n...\n-----END RSA PRIVATE KEY-----',
	},
});

console.log(config); // outputs the generated config as an ArrayBuffer
```

For adhoc configs:

```ts
import { Config } from 'clipgen';

let config = await Config.render({
	type: 'adhoc',
	items: [
		{
			name: 'App Name',
			url: 'https://example.com/App.ipa',
			icon: 'https://example.com/AppIcon.png',
			identifier: 'com.example.app',
		},
	],
});

console.log(config); // outputs the generated config as an ArrayBuffer
```
