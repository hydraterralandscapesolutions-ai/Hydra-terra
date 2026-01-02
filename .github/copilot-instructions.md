# Copilot Instructions for HYDRA-TERRA

## Project Overview
This repository contains the official website for HYDRA-TERRA Landscape Solutions (HYDRA-TERRA.COM.AU), a professional landscaping services company based in Australia.

## Repository Structure
- `index.html` - Main website landing page with company information and contact details
- `Cname` - Custom domain configuration for GitHub Pages
- `README.md` - Project documentation
- Logo and icon assets (`logo_*.png`, `icon_*.png`) - Brand identity files

## Website Technology Stack
- **Frontend**: Static HTML with inline CSS
- **Hosting**: GitHub Pages
- **Domain**: HYDRA-TERRA.COM.AU

## Coding Standards and Conventions

### HTML
- Use semantic HTML5 elements where appropriate
- Maintain inline styles for simplicity (no separate CSS file currently)
- Keep responsive design considerations (mobile-first approach)
- Follow accessibility best practices (alt text for images, proper heading hierarchy)

### Styling
- Use system fonts: `system-ui, Segoe UI, Arial`
- Color palette:
  - Primary background: `#111827` (dark)
  - Text: `#e8eefc` (light)
  - Accent: `#1f2937` (buttons/cards)
  - Success/WhatsApp: `#16a34a` (green)
- Border radius: `8px` for buttons, `10-12px` for cards/images
- Maintain consistent spacing and padding

### Images
- Optimize images for web (PNG format currently used)
- Provide multiple sizes where appropriate (e.g., logo_400.png, logo_800.png)
- Include descriptive alt text for accessibility

## Content Guidelines
- Company name variations (maintain existing usage in each context):
  - Display name: `HYDRA-TERRA` (all caps with hyphen) - used in headings and titles
  - Repository/README: `Hydra-terra` (title case with hyphen)
  - Social media handles: `hydraterra` (lowercase, no hyphen) - @hydraterra.com.au
- Domain: HYDRA-TERRA.COM.AU
- Social media platforms supported: Instagram, Facebook, TikTok, Google, WhatsApp
- Contact number: +61 426 398 510

## Deployment
- **Platform**: GitHub Pages
- **Branch**: Changes are deployed from the main/default branch
- **Custom Domain**: Configured via CNAME file
- **Process**: Push to main branch triggers automatic deployment

## Best Practices
1. **Always preserve existing functionality** - This is a production website
2. **Test responsive design** - Ensure changes work on mobile, tablet, and desktop
3. **Validate HTML** - Use W3C validator or similar tools
4. **Optimize assets** - Compress images and minimize file sizes
5. **Maintain brand consistency** - Follow the established color scheme and design patterns
6. **Test all links** - Ensure social media and contact links work correctly
7. **Accessibility** - Maintain WCAG compliance where possible

## Common Tasks

### Adding New Social Media Links
- Add to the social links section in `index.html`
- Use consistent button styling
- Ensure target="_blank" for external links

### Updating Gallery Images
- Replace placeholder divs with actual images
- Use optimized image files
- Maintain grid layout responsiveness

### Modifying Contact Information
- Update WhatsApp link (e.g., `href="https://wa.me/61426398510"`)
- Update social media URLs
- Update QR code images if contact methods change

## Testing
- **Visual Testing**: Open `index.html` in multiple browsers (Chrome, Firefox, Safari)
- **Mobile Testing**: Use browser dev tools to test responsive design
- **Link Testing**: Verify all external links work correctly
- **Performance**: Check page load speed and optimize if needed

## Notes
- This is a simple static website - avoid over-engineering
- Keep dependencies minimal (no build process required)
- Focus on clarity, performance, and user experience
- When in doubt, maintain the existing simple, straightforward approach
