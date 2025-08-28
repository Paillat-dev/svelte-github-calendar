# svelte-github-calendar

A Svelte wrapper of the [github-calendar](https://github.com/Bloggify/github-calendar) library to displays GitHub contribution graphs in your Svelte applications.

## Installation

```bash
npm install svelte-github-calendar
```

## Usage

### Basic Example

```svelte
<script>
	import { GithubCalendar } from 'svelte-github-calendar';
</script>

<GithubCalendar username="yourusername" />
```

### Advanced Example

```svelte
<script>
	import { GithubCalendar } from 'svelte-github-calendar';
</script>

<GithubCalendar
	username="yourusername"
	summary_text="Summary of {name}'s GitHub activity"
	global_stats={true}
	responsive={true}
	tooltips={true}
	cache={60}
	class="my-custom-class"
/>
```

## Props

| Prop           | Type       | Default      | Description                              |
| -------------- | ---------- | ------------ | ---------------------------------------- |
| `username`     | `string`   | **Required** | GitHub username to display calendar for  |
| `summary_text` | `string`   | `undefined`  | Custom summary text template.            |
| `proxy`        | `function` | `undefined`  | Custom proxy function for API requests   |
| `global_stats` | `boolean`  | `undefined`  | Whether to show global statistics        |
| `responsive`   | `boolean`  | `undefined`  | Enable responsive design                 |
| `tooltips`     | `boolean`  | `undefined`  | Enable hover tooltips                    |
| `cache`        | `number`   | `undefined`  | Cache duration in seconds                |
| `class`        | `string`   | `''`         | Additional CSS classes for the container |

You can read more about the props in the [original documentation](https://github.com/Bloggify/github-calendar).

## Credits

- Svelte wrapper of [github-calendar](https://github.com/Bloggify/github-calendar) by Bloggify
- Designed specifically for Svelte applications

## License

This library is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Feel free to:

- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## Troubleshooting

### Calendar not loading

- Ensure the username is valid and public
- Verify network connectivity
