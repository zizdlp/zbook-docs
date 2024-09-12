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
