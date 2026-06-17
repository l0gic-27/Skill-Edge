# skilledge - AI-Powered Resume Analyzer (React Frontend)

A modern, AI-powered resume analysis tool built with React. Upload your PDF resume and get instant insights, skill recommendations, experience level analysis, and personalized interview questions.

## ⚠️ IMPORTANT: API KEY NOTICE

**This version has the Groq API key hardcoded for TEAM REVIEW purposes only.**

Before running the app, you **MUST** update the API key in:
```
src/utils/groqAPI.js
```

Replace `YOUR_GROQ_API_KEY_HERE` with your actual Groq API key.

Get a free API key at: https://console.groq.com

**🚨 DO NOT commit this code to public repositories with a real API key!**

## Features

✅ **PDF Resume Parsing** - Extract text from PDF resumes using PDF.js  
✅ **Smart Skill Detection** - Identifies 100+ technical skills automatically  
✅ **Field Prediction** - Predicts career field based on skills  
✅ **Experience Level Analysis** - Determines Fresher/Intermediate/Experienced  
✅ **Resume Scoring** - 100-point comprehensive scoring system  
✅ **AI-Powered Interview Questions** - Personalized questions via Groq AI  
✅ **Skills Gap Analysis** - Shows what skills to learn  
✅ **Beautiful Apple-Inspired UI** - Dark mode design system  

## Tech Stack

- **React 18** - Frontend framework
- **Vite** - Build tool and dev server
- **PDF.js** - PDF parsing in browser
- **Recharts** - Data visualizations
- **Lucide React** - Icon library
- **Groq AI** - LLaMA 3.3 for interview questions

## Installation

1. **Navigate to the project directory:**
   ```bash
   cd react-frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Add your Groq API Key:**
   
   Open `src/utils/groqAPI.js` and replace:
   ```javascript
   const GROQ_API_KEY = 'YOUR_GROQ_API_KEY_HERE';
   ```
   
   with your actual API key from https://console.groq.com

4. **Start the development server:**
   ```bash
   npm run dev
   ```

5. **Open your browser:**
   
   Navigate to `http://localhost:3000`

## Usage

1. **Upload Resume**: Click or drag-drop your PDF resume
2. **Wait for Analysis**: The app parses and analyzes your resume (5-10 seconds)
3. **View Results**: 
   - Resume score and breakdown
   - Detected skills
   - Experience level
   - Recommended skills
   - Skills gap analysis
   - AI-generated interview questions
4. **Analyze Another**: Click "Analyze Another Resume" to start over

## Project Structure

```
react-frontend/
├── src/
│   ├── components/
│   │   ├── Header.jsx              # App header
│   │   ├── UploadSection.jsx       # Resume upload UI
│   │   ├── ResultsDisplay.jsx      # Main results component
│   │   ├── ScoreCircle.jsx         # Circular score visualization
│   │   ├── SkillsAnalysis.jsx      # Skills breakdown
│   │   └── InterviewQuestions.jsx  # Interview prep section
│   ├── utils/
│   │   ├── pdfParser.js            # PDF text extraction
│   │   ├── skillDetector.js        # Skill detection logic
│   │   ├── resumeScorer.js         # Scoring algorithm
│   │   └── groqAPI.js              # ⚠️ API key hardcoded here
│   ├── App.jsx                     # Main app component
│   ├── App.css                     # App styles
│   ├── index.css                   # Global styles
│   └── main.jsx                    # Entry point
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

## Build for Production

```bash
npm run build
```

This creates a `dist/` folder with optimized production files.

## Deployment

### Vercel (Recommended)
1. Push code to GitHub (remove API key first!)
2. Import project in Vercel
3. Add environment variable: `VITE_GROQ_API_KEY`
4. Deploy

### Netlify
1. Build the project: `npm run build`
2. Drag-drop `dist/` folder to Netlify
3. Configure environment variables

## Environment Variables (For Production)

For production, move the API key to environment variables:

1. Create `.env` file:
   ```
   VITE_GROQ_API_KEY=your_actual_api_key_here
   ```

2. Update `src/utils/groqAPI.js`:
   ```javascript
   const GROQ_API_KEY = import.meta.env.VITE_GROQ_API_KEY;
   ```

3. Add `.env` to `.gitignore`

## Features in Detail

### Resume Scoring (100 points)
- Objective/Summary: 6 pts
- Education: 12 pts
- Experience: 16 pts
- Internships: 6 pts
- Skills: 7 pts
- Hobbies: 4 pts
- Interests: 5 pts
- Achievements: 13 pts
- Certifications: 12 pts
- Projects: 19 pts

### Skill Detection
Detects 100+ skills across:
- Programming Languages (Python, Java, JavaScript, etc.)
- Web Frameworks (React, Angular, Django, etc.)
- Databases (SQL, MongoDB, PostgreSQL, etc.)
- Cloud & DevOps (AWS, Docker, Kubernetes, etc.)
- Data Science & ML (TensorFlow, PyTorch, Pandas, etc.)

### Experience Level Detection
Analyzes:
- Years of experience mentioned
- Work duration from date ranges
- Graduation year
- Internship presence
- Job position count

## Limitations

- **PDF Support**: Only text-based PDFs (not scanned images)
- **API Costs**: Groq API usage may incur costs beyond free tier
- **Browser Dependency**: Requires modern browser with ES6+ support

## Security Considerations

⚠️ **Never expose API keys in frontend code for production**

Current setup (hardcoded API key) is **ONLY for team review**. For production:
1. Use environment variables
2. Implement a backend proxy
3. Use serverless functions (Vercel/Netlify)
4. Implement rate limiting

## License

MIT License - Feel free to use for personal/commercial projects

## Support

For issues or questions, contact the development team.

---

**Made with ❤️ using React + Groq AI**
