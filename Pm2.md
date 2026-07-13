## Project build

Step-1: New Project Case, Git Clone otherwise Git Pull

Step-2: nano .env - Edit environment variables - Save => Ctr + O - Confirm => Ctr - Exit => Ctr + X

Step-3: npm install

Step-4: npm run build

Step-5: PORT=<PortNumber> pm2 start npm --name <PortNumber_As_Note>-<AppName> --cwd --run dev --p <PortNumber>

Step-6: pm2 log <id>

## Nginx build - Configure reverse proxy to PM2 app

    Step-1: Edit => cd /etc/nginx/sites-available/<domain> -
    Step-2: ln -s /etc/nginx/sites-available/<domain> /etc/nginx/sites-enabled/ -
    Step-3: nginx -t && systemctl reload nginx
    Step-4: systemctl status nginx
