# Deployment Guide for ICS/SCADA Training Platform

This guide provides step-by-step instructions for deploying the ICS/SCADA Training Platform to Vercel.

## Prerequisites

- Git installed on your local machine
- Node.js 18+ installed (for local development)
- A Vercel account (free tier available)

## Method 1: Deploy via Vercel CLI (Recommended)

### Step 1: Prepare Your Project
1. Create a new directory for your project:
   ```bash
   mkdir ics-scada-training
   cd ics-scada-training
   ```

2. Save all the provided files in this directory:
   - `index.html`
   - `package.json`
   - `vercel.json`
   - `README.md`
   - `.gitignore`

### Step 2: Install Vercel CLI
```bash
npm install -g vercel
```

### Step 3: Login to Vercel
```bash
vercel login
```
Follow the prompts to authenticate with your Vercel account.

### Step 4: Deploy
```bash
vercel --prod
```

The CLI will:
- Detect that this is a static site
- Upload your files
- Provide you with a live URL
- Set up automatic deployments for future updates

## Method 2: Deploy via Vercel Dashboard

### Step 1: Prepare Your Repository
1. Create a new repository on GitHub, GitLab, or Bitbucket
2. Upload all project files to the repository
3. Commit and push your changes

### Step 2: Connect to Vercel
1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "New Project"
3. Import your repository
4. Vercel will automatically detect the configuration

### Step 3: Deploy
1. Click "Deploy"
2. Wait for the build to complete
3. Your site will be live at the provided URL

## Method 3: Drag and Drop Deployment

### Step 1: Prepare Files
1. Create a folder with all project files
2. Ensure `index.html` is in the root directory

### Step 2: Upload to Vercel
1. Go to [vercel.com](https://vercel.com)
2. Drag and drop your project folder onto the dashboard
3. Vercel will automatically deploy your static site

## Post-Deployment Configuration

### Custom Domain Setup
1. In your Vercel dashboard, go to your project
2. Navigate to "Settings" → "Domains"
3. Add your custom domain
4. Configure DNS records as instructed

### Environment Variables (if needed)
1. Go to "Settings" → "Environment Variables"
2. Add any required environment variables
3. Redeploy if necessary

### SSL Certificate
- Vercel automatically provides SSL certificates
- Your site will be available over HTTPS immediately

## LMS Integration Setup

### For SCORM/cmi5 LMS Integration:
1. **Activity Package**: Create a zip file containing:
   - `index.html` (main file)
   - `imsmanifest.xml` (SCORM manifest)
   - `cmi5.xml` (cmi5 course structure)

2. **Launch URL**: Use your Vercel URL with parameters:
   ```
   https://your-project.vercel.app/?endpoint={LMS_ENDPOINT}&auth={AUTH_TOKEN}&actor_name={LEARNER_NAME}
   ```

### Sample cmi5.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<courseStructure xmlns="https://w3id.org/xapi/profiles/cmi5/v1.0/coursestructure.xsd">
    <course id="http://example.com/ics-scada-training">
        <title>
            <langstring lang="en-US">ICS/SCADA Security Training</langstring>
        </title>
        <description>
            <langstring lang="en-US">Comprehensive training on Industrial Control Systems and SCADA security</langstring>
        </description>
        <au id="http://example.com/ics-scada-training/module1" moveOn="Completed" masteryScore="0.8">
            <title>
                <langstring lang="en-US">ICS/SCADA Training Modules</langstring>
            </title>
            <url>index.html</url>
        </au>
    </course>
</courseStructure>
```

## Monitoring and Analytics

### Built-in Vercel Analytics
1. Go to your project dashboard
2. Navigate to "Analytics"
3. View performance metrics and usage statistics

### Custom Analytics Integration
Add analytics code to your `index.html` before the closing `</body>` tag:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## Performance Optimization

### Already Optimized Features:
- ✅ Static file serving
- ✅ Global CDN distribution
- ✅ Automatic compression
- ✅ Optimized caching headers
- ✅ Security headers configured

### Additional Optimizations:
1. **Image Optimization**: If adding images, use WebP format
2. **Code Minification**: Already optimized for production
3. **Progressive Loading**: Consider implementing for large datasets

## Troubleshooting

### Common Issues:

1. **404 Errors**: Ensure `index.html` is in the root directory
2. **CSP Violations**: Check console for Content Security Policy errors
3. **LMS Integration Issues**: Verify xAPI endpoint configuration

### Debug Mode:
Add `?debug=true` to your URL to enable console logging:
```
https://your-project.vercel.app/?debug=true
```

### Support Resources:
- [Vercel Documentation](https://vercel.com/docs)
- [cmi5 Specification](https://github.com/AICC/CMI-5_Spec_Current)
- [xAPI Documentation](https://github.com/adlnet/xAPI-Spec)

## Updating Your Deployment

### For Git-based Deployments:
1. Make changes to your files
2. Commit and push to your repository
3. Vercel automatically redeploys

### For CLI Deployments:
1. Make changes to your files
2. Run `vercel --prod` again
3. Vercel will update your deployment

### Rollback if Needed:
1. Go to your Vercel dashboard
2. Navigate to "Deployments"
3. Click "Promote to Production" on a previous deployment

## Security Considerations

### Headers Already Configured:
- Content Security Policy (CSP)
- X-Frame-Options
- X-Content-Type-Options
- X-XSS-Protection

### Additional Security:
1. Regular dependency updates
2. Monitor for security vulnerabilities
3. Use HTTPS for all external integrations
4. Validate all user inputs

## Cost Considerations

### Vercel Pricing:
- **Hobby Plan**: Free for personal projects
- **Pro Plan**: $20/month for commercial use
- **Enterprise**: Custom pricing for large organizations

### Usage Limits (Hobby Plan):
- 100GB bandwidth per month
- 1000 serverless function invocations per day
- 100 deployments per day

For training platforms with high usage, consider the Pro plan for unlimited bandwidth and higher limits.