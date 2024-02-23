# React + Vite + Docker

This template provides a minimal setup to get React working in Vite using Docker and Docker compose for development and production

## Development workflow

To run the project in dev mode:

```
docker compose watch -d
```

Docker compose automatically watches for changes to files and rebuilds the container if `package.json` changes

```
docker compose logs -f web
```

To install any NPM package

Add the package name and version to `package.json`. Docker will automatically install the package and make sure it's synced to the host

To stop the container

```
docker compose down
```

## Expanding the ESLint configuration

If you are developing a production application, it's recommended to update the configuration to enable type aware lint rules:

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
