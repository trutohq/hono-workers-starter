# Hono Workers Starter

A modern starter template for building Cloudflare Workers applications using Hono framework.

## Tech Stack

- [Hono](https://hono.dev/) - Fast, lightweight web framework
- [Cloudflare Workers](https://workers.cloudflare.com/) - Edge computing platform
- [TypeScript](https://www.typescriptlang.org/) - Type-safe JavaScript
- [Wrangler](https://developers.cloudflare.com/workers/wrangler/) - CLI for Cloudflare Workers
- [ESLint](https://eslint.org/) - Code linting
- [Prettier](https://prettier.io/) - Code formatting
- [Husky](https://typicode.github.io/husky/) - Git hooks
- [lint-staged](https://github.com/okonet/lint-staged) - Run linters on staged files
- [Volta](https://volta.sh/) - JavaScript tool manager

## Prerequisites

- [Volta](https://volta.sh/) for Node.js version management
- [Cloudflare account](https://dash.cloudflare.com/sign-up)

## Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/trutohq/hono-workers-starter.git
   cd hono-workers-starter
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

## Development

The project uses Volta to manage Node.js and package manager versions. The following versions are pinned:

- Node.js: 18.18.0
- npm: 10.2.5
- Yarn: 4.9.1

### Available Scripts

- `npm run dev` - Start development server
- `npm run deploy` - Deploy to Cloudflare Workers
- `npm run cf-typegen` - Generate Cloudflare Workers types
- `npm run lint` - Run ESLint
- `npm run lint:fix` - Fix ESLint issues
- `npm run format` - Format code with Prettier
- `npm run format:check` - Check code formatting

### Code Quality

The project uses several tools to maintain code quality:

- ESLint for code linting
- Prettier for code formatting
- Husky for Git hooks
- lint-staged for running linters on staged files

Git hooks are automatically set up when you run `npm install`. They will:

- Format code with Prettier
- Run ESLint
- Check for TypeScript errors

## Deployment

To deploy your application to Cloudflare Workers:

1. Configure your Cloudflare credentials:

   ```bash
   wrangler login
   ```

2. Deploy the application:
   ```bash
   npm run deploy
   ```

## Project Structure

```
.
├── src/              # Source code
│   ├── index.ts      # Application entry point
│   └── routes/       # Route handlers
├── .eslintrc.json   # ESLint configuration
├── .prettierrc      # Prettier configuration
├── package.json     # Project dependencies and scripts
└── wrangler.toml    # Cloudflare Workers configuration
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```txt
npm install
npm run dev
```

```txt
npm run deploy
```

[For generating/synchronizing types based on your Worker configuration run](https://developers.cloudflare.com/workers/wrangler/commands/#types):

```txt
npm run cf-typegen
```

Pass the `CloudflareBindings` as generics when instantiation `Hono`:

```ts
// src/index.ts
const app = new Hono<{ Bindings: CloudflareBindings }>();
```
