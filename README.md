# React + Vite + Docker

This template provides a minimal setup to get React working in Vite using Docker and Docker compose for development

## Development workflow

If pulled for the first time or the `package.json` has changed run

```
docker compose build
```

Then, run the following command to start the environment

```
docker compose up -d
```

To check the logs

```
docker compose logs -f web
```

To install any NPM package

```
docker compose exec web pnpm i <package-name>
```

To stop the container

```
docker compose down
```

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json'],
    tsconfigRootDir: __dirname,
  },
};
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list
