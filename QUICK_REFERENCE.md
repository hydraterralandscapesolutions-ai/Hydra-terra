# Quick Reference - Branch & DNS Settings

## ❓ Which branch to use?

**Answer: Use the `main` branch**

All production deployments should go through the `main` branch. When you merge changes to `main`, GitHub Pages automatically deploys your website.

## 🌐 What are the DNS settings?

**Domain**: HYDRA-TERRA.COM.AU

### DNS Configuration

Configure these records with your domain registrar (e.g., GoDaddy, Namecheap, etc.):

#### For Apex Domain (@):
```
A Record → 185.199.108.153
A Record → 185.199.109.153
A Record → 185.199.110.153
A Record → 185.199.111.153
```

#### For www Subdomain:
```
CNAME → www → HYDRA-TERRA.COM.AU
```

## 📚 Need more details?

See [DEPLOYMENT.md](./DEPLOYMENT.md) for complete deployment instructions, troubleshooting, and GitHub Pages configuration.

## ✅ Quick Checklist

- [ ] DNS A records configured (4 records)
- [ ] CNAME record configured for www
- [ ] GitHub Pages source set to `main` branch
- [ ] Custom domain added in GitHub repository settings
- [ ] Wait 24-48 hours for DNS propagation
- [ ] Enable HTTPS once DNS is verified
- [ ] Test website at https://HYDRA-TERRA.COM.AU
