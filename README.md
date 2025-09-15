

- **Personal Information**: Name, title, description
- **Accent Color**: Primary color theme (changing this will change the accent color site wide)
- **Social Links**: Email, LinkedIn, Twitter, GitHub (all optional)
- **About Section**: Personal bio/description
- **Skills**: List of technical skills
- **Projects**: Project showcase with descriptions and links
- **Experience**: Work history with bullet points
- **Education**: Educational background and achievements

If skills, projects, experience, or education are removed from the config, those sections will be hidden entirely.

### Example structures

Here's what the config data structure looks like for each section:

#### Basic Information
```typescript
name: "Your Name",
title: "Your Job Title",
description: "Brief site description",
accentColor: "#1d4ed8", // Hex color for theme
```

#### Social Links (all optional)
```typescript
social: {
  email: "your-email@example.com",
  linkedin: "https://linkedin.com/in/yourprofile",
  twitter: "https://twitter.com/yourprofile", 
  github: "https://github.com/yourusername",
}
```

#### About Section
```typescript
aboutMe: "A paragraph describing yourself, your background, interests, and what you're passionate about. This appears in the About section of your portfolio."
```

#### Skills
```typescript
skills: ["JavaScript", "React", "Node.js", "Python", "AWS", "Docker"]
```

#### Projects
```typescript
projects: [
  {
    name: "Project Name",
    description: "Brief description of what the project does and its impact",
    link: "https://github.com/yourusername/project",
    skills: ["React", "Node.js", "AWS"], // Technologies used
  }
]
```

#### Experience
```typescript
experience: [
  {
    company: "Company Name",
    title: "Your Job Title",
    dateRange: "Jan 2022 - Present",
    bullets: [
      "Led development of microservices architecture serving 1M+ users",
      "Reduced API response times by 40% through optimization",
      "Mentored team of 5 junior developers",
    ],
  }
]
```

#### Education
```typescript
education: [
  {
    school: "University Name",
    degree: "Bachelor of Science in Computer Science",
    dateRange: "2014 - 2018",
    achievements: [
      "Graduated Magna Cum Laude with 3.8 GPA",
      "Dean's List all semesters",
      "President of Computer Science Club"
    ]
  }
]

