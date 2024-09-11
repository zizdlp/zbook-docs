# Frontend

## Dependencies

Frontend development requires the installation of `npm`. Below are some commands to set up the environment:

```bash
sudo apt update
sudo apt install nodejs npm
sudo npm install -g npm@latest
npm install
npm run build
```

## Running

"Create a `.env.local` file under the `zbook_frontend/` directory, and copy the contents of `.env.production` into it. For example, you can set `AUTH_URL` to `http://localhost:3000` in development mode. For similar parameters, you can refer to `compose.env` for configuration."

To start the frontend server, use the following command:

```bash
make next
```

## Adding Language Support

ZBook currently supports Simplified Chinese and English. To add support for a new language, you'll need to modify the following:

- `zbook_frontend/messages`: Add the corresponding files and complete the content, such as `fr.json`.
- `zbook_frontend/src/navigation.ts`: Add the new language to `locales`.
- `zbook_frontend/global.d.ts`: Append the new language.
- `zbook_frontend/src/components/navbars/NavTheme.tsx`: Append the new language to `localeMap`.
