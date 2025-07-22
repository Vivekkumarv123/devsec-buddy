
# DevSec Buddy

**DevSec Buddy** is a full-stack web vulnerability scanner designed to help developers identify and fix common website security issues like CSRF, XSS, missing security headers, and more.

This project consists of a **frontend** built with Next.js and a **backend** powered by Node.js and Python. The system offers real-time scans, security scores, vulnerability insights, and detailed remediation guidance using a sleek, modern interface.

---

## Tagline

**DevSec Buddy — Your Developer-Sidekick for Securing the Web**

---

## Features

### Frontend

* Website security scan form with animated UI
* Visual security score (circular progress bar)
* Vulnerability detection and real-time parsing (CSRF, XSS, etc.)
* Remediation tips rendered with markdown
* Scan history with timestamps
* Responsive and mobile-friendly UI
* Smooth animations using Framer Motion

### Backend

* REST API to trigger scans with custom options
* Modular scan profiles: `basic`, `standard`, `deep`
* Python scanner integration for advanced analysis
* Render cold-start handling for better performance
* JSON output with error handling

---

## Tech Stack
```
| Tech                | Used For                         |
| ------------------- | -------------------------------- |
| Next.js             | Frontend framework (React + SSR) |
| Tailwind CSS        | Styling (utility-first CSS)      |
| Framer Motion       | UI animations                    |
| Axios               | HTTP client (frontend & backend) |
| React Markdown      | Render remediation markdown      |
| Node.js (ESM)       | Backend server                   |
| Express.js          | API routes                       |
| Python 3.8+         | Vulnerability scanning logic     |
| Firebase (optional) | Realtime DB for scan storage     |
```
---

## Folder Structure

```
devsec-buddy/
├── frontend/
│   ├── components/
│   ├── public/
│   ├── app/ or pages/
│   ├── tailwind.config.js
│   └── package.json
│
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── scanner/       # Python scanner lives here
│   ├── index.js       # Express server
│   └── package.json
```

---

## Frontend Setup

1. Clone the frontend:

   ```
   git clone https://github.com/your-username/devsec-buddy-frontend.git
   cd devsec-buddy/frontend
   ```

2. Install dependencies:

   ```
   npm install
   ```

3. Create a `.env` file:

   ```
   NEXT_PUBLIC_API_URL=http://localhost:5000
   ```

4. Run the dev server:

   ```
   npm run dev
   ```

---

## Backend Setup

1. Clone the backend:

   ```
   git clone https://github.com/your-username/devsec-buddy.git
   cd devsec-buddy/backend
   ```

2. Install dependencies:

   ```
   npm install
   ```

3. Ensure you have Python 3.8+ and your `scanner/main.py` script is ready.

4. Start the dev server:

   ```
   npm run dev
   ```

---

## API Endpoint

### POST `/api/scan`

Trigger a security scan with optional configuration.

#### Request Body

```json
{
  "url": "https://target-site.com",
  "profile": "basic",
  "method": "POST",
  "data": { "username": "admin" },
  "headers": { "Authorization": "Bearer token" },
  "cookies": { "session": "abc123" }
}
```

#### Sample Response

```json
{
  "success": true,
  "results": {
    "vulnerabilities": [...],
    "summary": { "score": 72, "severity": "medium" }
  }
}
```

---

## Render Cold Start Optimization

For backend hosted on Render, the frontend auto-pings:

```js
if (input.url.includes("devsec-buddy-backend.onrender.com")) {
  await axios.get("https://devsec-buddy-backend.onrender.com/healthz");
}
```

This reduces the wait time from cold starts.

---

## Contributing

Pull requests are welcome.

1. Fork the repo
2. Create your feature branch:
   `git checkout -b feature/my-feature`
3. Commit and push:
   `git commit -m "Add feature"`
   `git push origin feature/my-feature`
4. Open a Pull Request

---

## License

This project is licensed under the **MIT License**.

---

## Credits

Created by **Vivek Kumar Verma**

* LinkedIn: [linkedin.com/in/vivek-kumar-verma-programmer-information-technology](https://www.linkedin.com/in/vivek-kumar-verma-programmer-information-technology/)
* GitHub: [github.com/Vivekkumarv123](https://github.com/Vivekkumarv123)
