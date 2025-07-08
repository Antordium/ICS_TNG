# ICS/SCADA Training Platform

A comprehensive cybersecurity training platform focused on Industrial Control Systems (ICS) and Supervisory Control and Data Acquisition (SCADA) systems. This application provides interactive learning modules, assessments, and a capstone project to educate users about ICS/SCADA security.

## Features

- **Interactive Learning Modules**: Two comprehensive modules covering ICS/SCADA fundamentals and threat landscapes
- **Knowledge Assessments**: Built-in quizzes and assessments with immediate feedback
- **Capstone Project**: Hands-on cyber range simulations for practical application
- **Progress Tracking**: Real-time progress monitoring with visual indicators
- **Certificate Generation**: Automatic certificate generation upon successful completion
- **cmi5/xAPI Integration**: Full Learning Management System (LMS) compatibility
- **Responsive Design**: Mobile-friendly interface that works across all devices

## Course Content

### Module 1: Introduction to ICS and SCADA Systems
- Basic architecture and components
- Common ICS/SCADA environments
- The Purdue Model for network segmentation
- Key security concepts

### Module 2: ICS/SCADA Threat Landscape
- Common threats (malware, insider threats, ransomware)
- System vulnerabilities
- Adversary tactics, techniques, and procedures (TTPs)
- Real-world attack scenarios

### Capstone Project
- Water treatment plant ransomware scenario
- Power grid network segmentation task
- Insider threat detection simulation

## Technology Stack

- **Frontend**: Pure HTML5, CSS3, and vanilla JavaScript
- **Styling**: Custom CSS with modern design principles
- **Standards**: cmi5/xAPI compliant for LMS integration
- **Deployment**: Optimized for Vercel static hosting

## Deployment Instructions

### Quick Deploy to Vercel

1. **Clone or download this repository**
2. **Install Vercel CLI** (if not already installed):
   ```bash
   npm install -g vercel
   ```
3. **Deploy to Vercel**:
   ```bash
   vercel --prod
   ```

### Manual Deployment

1. **Upload files to Vercel dashboard**:
   - Go to [vercel.com](https://vercel.com)
   - Create a new project
   - Upload the entire project folder
   - Vercel will automatically detect the static site configuration

### Custom Domain Setup

1. In your Vercel dashboard, go to your project settings
2. Navigate to "Domains"
3. Add your custom domain
4. Follow the DNS configuration instructions

## Configuration

### LMS Integration

The application supports cmi5/xAPI integration out of the box. To connect to an LMS:

1. **URL Parameters**: The application accepts standard cmi5 launch parameters:
   - `endpoint`: xAPI endpoint URL
   - `auth`: Authentication token
   - `activityId`: Activity identifier
   - `registration`: Registration UUID
   - `actor_name`: Learner name
   - `actor_email`: Learner email

2. **Example Launch URL**:
   ```
   https://your-domain.vercel.app/?endpoint=https://lms.example.com/xapi/&auth=Basic_TOKEN&actor_name=John_Doe&actor_email=john@example.com
   ```

### Customization

- **Branding**: Update the logo and colors in the CSS section
- **Content**: Modify the module content directly in the HTML
- **Assessment Scoring**: Adjust passing scores in the JavaScript functions
- **Progress Tracking**: Customize progress calculation logic

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Security Features

- Content Security Policy (CSP) headers
- XSS protection
- Frame options for clickjacking prevention
- Secure external resource loading from CDNJS only

## File Structure

```
ics-scada-training/
├── index.html          # Main application file
├── package.json        # Node.js package configuration
├── vercel.json        # Vercel deployment configuration
├── README.md          # This documentation
└── .gitignore         # Git ignore rules
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For technical support or questions:
- Create an issue in the repository
- Contact the development team
- Refer to the cmi5/xAPI documentation for LMS integration questions

## Changelog

### Version 1.0.0
- Initial release
- Two complete learning modules
- Full cmi5/xAPI integration
- Responsive design implementation
- Certificate generation
- Progress tracking