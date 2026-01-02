# Deployment Guide for HYDRA-TERRA Website

## Which Branch to Use

**Use the `main` branch for deployment.**

This repository is configured to deploy to GitHub Pages from the `main` branch. When you merge changes to the `main` branch, GitHub Pages will automatically build and deploy your website.

### Current Setup
- **Production Branch**: `main`
- **Custom Domain**: HYDRA-TERRA.COM.AU
- **GitHub Pages URL**: https://hydraterralandscapesolutions-ai.github.io/Hydra-terra/

## DNS Settings for Custom Domain

To make your website live at **HYDRA-TERRA.COM.AU**, you need to configure the following DNS records with your domain registrar:

### Option 1: CNAME Record (Recommended for www subdomain)
```
Type: CNAME
Name: www
Value: hydraterralandscapesolutions-ai.github.io
TTL: 3600 (or your registrar's default)
```

### Option 2: A Records (For apex domain @)
If you want to use the root domain (without www), configure these A records:

```
Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

### Both www and apex domain (Recommended)
For best results, configure both:
1. Add all 4 A records for the apex domain (@)
2. Add a CNAME record for www pointing to your apex domain:
   ```
   Type: CNAME
   Name: www
   Value: hydra-terra.com.au
   TTL: 3600
   ```

## GitHub Pages Configuration

1. Go to your repository settings: https://github.com/hydraterralandscapesolutions-ai/Hydra-terra/settings/pages

2. Under "Source", ensure:
   - **Branch**: `main`
   - **Folder**: `/ (root)`

3. Under "Custom domain":
   - Enter: `HYDRA-TERRA.COM.AU` (or `www.hydra-terra.com.au`)
   - Click "Save"
   - Wait for DNS check to complete
   - Enable "Enforce HTTPS" once DNS propagation is complete

## Deployment Process

1. **Make changes** on a feature branch (like `copilot/dns-settings-configuration`)
2. **Test your changes** locally if possible
3. **Create a Pull Request** to merge into `main`
4. **Review and merge** the PR
5. **GitHub Pages automatically deploys** from `main` branch (usually within 1-2 minutes)
6. **Visit your site** at https://HYDRA-TERRA.COM.AU

## Troubleshooting

### DNS Not Working
- DNS propagation can take 24-48 hours
- Use a tool like https://dnschecker.org to verify your DNS records
- Ensure the CNAME file in your repository contains exactly: `HYDRA-TERRA.COM.AU`

### Site Not Updating
- Check GitHub Actions for deployment status
- Clear your browser cache
- Wait a few minutes - GitHub Pages can take 1-10 minutes to deploy changes

### HTTPS Certificate Issues
- HTTPS may take up to 24 hours to provision after DNS is properly configured
- Ensure DNS records are correctly pointing to GitHub Pages
- Don't enable "Enforce HTTPS" until the certificate is ready

## Verifying Your Setup

1. **Check DNS**: Run `nslookup HYDRA-TERRA.COM.AU` - should resolve to GitHub Pages IPs
2. **Check GitHub Pages**: Repository Settings → Pages should show "Your site is published at https://HYDRA-TERRA.COM.AU"
3. **Test the site**: Visit https://HYDRA-TERRA.COM.AU in your browser

## Important Files

- **CNAME**: Contains your custom domain name (must be exactly `HYDRA-TERRA.COM.AU`)
- **index.html**: Your website homepage
- **README.md**: Project documentation

## Support

For more information about GitHub Pages and custom domains:
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Configuring a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
