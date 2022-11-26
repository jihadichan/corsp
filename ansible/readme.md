# Install

Create your server with SSH key + firewall to your home. This playbook **DOES NOT** set up any security.

```
ansible-playbook -i 23.88.103.113, -e ansible_user=root playbook.yml
```



# SSL cert

AnkiDroid does not allow HTTP calls to external resources for some reason, including API requests.

```
apt install certbot python3-certbot-nginx
certbot --nginx -d ssproxy.de -d www.ssproxy.de
```

Cert is only valid for 3 months. Cannot be increased, see [here](https://community.letsencrypt.org/t/how-to-set-expiration-date/79440). Disable firewall and renew via:

```
certbot renew
```

