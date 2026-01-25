# ASA Policy Frontend

Web application for the Augustana Students' Association (ASA) to manage, display, and provide access to organizational policies and bylaws.

**Live Site:** [https://asa-policy-frontend.vercel.app](https://asa-policy-frontend.vercel.app)

## Features

### Public Features
- **Policy Browsing**: View and browse active policies organized by sections:
  - Organizational Identity & Values
  - Governance & Elections
  - Operations, Staff & Finance
- **Bylaws Access**: Browse and download ASA bylaws in PDF format
- **Student Suggestions**: Submit policy suggestions with email verification
- **Search Functionality**: Search across policies and bylaws
- **Real-time Updates**: Automatic polling for newly approved policies
- **Policy Details**: View detailed policy information with PDF download capability
- **Contact Information**: Access ASA contact details and office hours

### Admin Features
- **Policy Management**: Create, edit, approve, and delete policies
- **Bylaw Management**: Create, edit, approve, and delete bylaws
- **Suggestion Management**: Review and manage student suggestions
- **Approval Workflow**: Approve or disapprove pending policies and bylaws
- **Dashboard**: Overview of all policies, bylaws, and suggestions

## Tech Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Custom CSS with responsive design
- **PDF Generation**: jsPDF library
- **API**: RESTful API integration
- **Hosting**: Vercel
- **Backend**: [asa-policy-backend](https://asa-policy-backend.onrender.com)

## Project Structure

```
asa-policy-frontend/
├── public/                 # Public-facing pages
│   ├── policies.html      # Main policies page
│   ├── policy-detail.html # Individual policy detail page
│   ├── bylaws.html        # Bylaws listing page
│   ├── bylaw-detail.html  # Individual bylaw detail page
│   ├── suggestions.html   # Student suggestions form
│   └── contact.html       # Contact information page
├── admin/                  # Admin dashboard pages
│   ├── login.html         # Admin login
│   ├── dashboard.html     # Admin dashboard
│   ├── policies.html      # Policy management
│   ├── bylaws.html        # Bylaw management
│   └── ...                # Other admin pages
├── css/                    # Stylesheets
│   ├── style.css          # Main stylesheet
│   ├── admin.css          # Admin-specific styles
│   └── responsive.css     # Responsive design styles
├── js/                     # JavaScript files
│   ├── public/            # Public-facing JavaScript
│   │   ├── policies.js    # Policies page logic
│   │   ├── bylaws.js      # Bylaws page logic
│   │   └── suggestions.js # Suggestions form logic
│   └── admin/             # Admin JavaScript
│       ├── login.js       # Admin authentication
│       ├── policies.js    # Policy management
│       ├── bylaws.js      # Bylaw management
│       └── ...            # Other admin scripts
├── assets/                 # Static assets
│   ├── asalogo.png        # ASA logo
│   └── ASABylaws.pdf      # Bylaws PDF document
├── vercel.json            # Vercel configuration
└── README.md              # This file
```

## Setup

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- Node.js (optional, for local development)
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/asa-policy-frontend.git
   cd asa-policy-frontend
   ```

2. **Open in a web server**
   
   Since this is a static site, you can use any local web server:
   
   **Using Python:**
   ```bash
   python -m http.server 8000
   ```
   
   **Using Node.js (http-server):**
   ```bash
   npx http-server -p 8000
   ```
   
   **Using VS Code Live Server:**
   - Install the "Live Server" extension
   - Right-click on `public/policies.html` and select "Open with Live Server"

3. **Access the application**
   - Open your browser and navigate to `http://localhost:8000/public/policies.html`

### API Configuration

The frontend connects to a backend API. By default, it uses:
```
https://asa-policy-backend.onrender.com
```

To configure a different API endpoint, you can set it in the browser console:
```javascript
window.API_BASE_URL = 'https://your-api-url.com';
```

Or modify the `API_BASE_URL` constant in the JavaScript files:
- `js/public/policies.js`
- `js/public/bylaws.js`
- `js/public/suggestions.js`

## Deployment

### Vercel Deployment

This project is configured for deployment on Vercel:

1. **Connect your repository to Vercel**
   - Import your GitHub repository in the Vercel dashboard
   - Vercel will automatically detect the project

2. **Configure build settings**
   - Framework Preset: **Other**
   - Output Directory: `.` (root directory)
   - Build Command: (leave empty for static sites)
   - Install Command: (leave empty)

3. **Environment Variables** (if needed)
   - Add any required environment variables in Vercel dashboard

4. **Deploy**
   - Vercel will automatically deploy on every push to the main branch

### Vercel Configuration

The `vercel.json` file configures routing:
- Root URL (`/`) redirects to `/public/policies.html`

## API Endpoints

The frontend expects the following backend API endpoints:

### Policies
- `GET /api/policies/approved` - Get all approved policies
- `GET /api/policies/approved?section={sectionName}` - Get policies by section
- `GET /api/policies/{policy_id}` - Get specific policy by ID

### Bylaws
- `GET /api/bylaws/approved` - Get all approved bylaws
- `GET /api/bylaws/{bylaw_id}` - Get specific bylaw by ID

### Suggestions
- `POST /api/suggestions` - Submit a new suggestion

### Admin (requires authentication)
- `POST /api/admin/login` - Admin login
- `GET /api/admin/policies` - Get all policies (admin)
- `POST /api/admin/policies` - Create new policy
- `PUT /api/admin/policies/{id}` - Update policy
- `DELETE /api/admin/policies/{id}` - Delete policy
- Similar endpoints for bylaws and suggestions

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is developed for the Augustana Students' Association.

## Contact

For questions or support, please contact:
- **Email**: augsa@ualberta.ca
- **Website**: [https://asa.su.ualberta.ca/](https://asa.su.ualberta.ca/)
- **Phone**: (780) 679-1541

## Acknowledgments

- Developed for the Augustana Students' Association
- Built with modern web technologies
- Hosted on Vercel
