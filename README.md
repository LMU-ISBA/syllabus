# Course Syllabus Template

A comprehensive template for creating course syllabi with integrated study guides, project documentation, and custom GPT configurations.

## Features

- **Interactive Syllabus Website** - Modern, responsive HTML syllabus with print optimization
- **Study Guide Templates** - Structured guides for midterm and final interviews
- **Project Documentation** - Requirements and milestone templates
- **Custom GPT Configurations** - Ready-to-use templates for:
  - Dataset Generator GPT (for student project data)
  - Interview Coach GPT (for interview practice)

## Creating a New Course

### Step 1: Create Repository from Template
1. Click the green **"Use this template"** button on GitHub
2. Name your new repository (e.g., `bcor-3750-fall-2025`)
3. Choose the `LMU-ISBA` organization as the owner
4. Click **"Create repository"**

### Step 2: Clone and Setup
```bash
# Clone your new course repository
git clone https://github.com/LMU-ISBA/your-course-repo.git
cd your-course-repo

# Link to template for future updates
git remote add template https://github.com/LMU-ISBA/syllabus.git

# Run the setup script (Phase 1)
./scripts/setup-course.sh
```

### Step 3: Complete Manual Edits (Phase 2)
The setup script handles core info. You'll still need to edit:
- **index.html**: Schedule, grading weights, policies, learning objectives
- **interviews/*.md**: Study guide content, sample questions
- **project/*.md**: Project details, milestone rubrics
- **gpts/**/*.md**: Domain-specific customizations
- **images/**: Add `header.jpg` for syllabus header

### Step 4: Commit and Deploy
```bash
git add -A
git commit -m "Configure: COURSE_CODE SEMESTER"
git push
```
GitHub Pages will automatically deploy your syllabus.

### Pulling Template Updates
When the template improves, pull updates into your course repo:
```bash
git fetch template
git merge template/main
# Resolve any conflicts, then commit
```

## Repository Structure

```
syllabus/
├── README.md                    # This file
├── index.html                   # Syllabus website template
├── LICENSE                      # MIT License
├── .gitignore
│
├── scripts/
│   └── setup-course.sh         # Interactive setup script
│
├── images/                      # Course images
│   └── .gitkeep                # Add header.jpg for syllabus
│
├── interviews/                  # Study guides
│   ├── README.md               # Guide for creating study guides
│   ├── midterm-study-guide.md  # Midterm interview template
│   └── final-study-guide.md    # Final interview template
│
├── project/                     # Project documentation
│   ├── README.md               # Guide for project design
│   ├── requirements.md         # Project requirements template
│   └── milestones.md           # Milestone breakdown template
│
├── gpts/                        # Custom GPT configurations
│   ├── README.md               # GPT setup guide
│   ├── dataset-generator/      # Dataset generation GPT
│   │   ├── instructions.md     # GPT system instructions
│   │   ├── ui-config.md       # OpenAI UI settings
│   │   └── knowledge/         # Upload course files here
│   └── interview-coach/        # Interview practice GPT
│       ├── instructions.md     # GPT system instructions
│       ├── ui-config.md       # OpenAI UI settings
│       └── knowledge/         # Upload study guides here
│
└── .github/workflows/
    └── pages.yml               # GitHub Pages deployment
```

## Customization Guide

### Syllabus Website (`index.html`)

1. Update the `<title>` tag with your course code and name
2. Modify CSS variables in `:root` for your institution's colors
3. Replace all `{{PLACEHOLDER}}` values:
   - `{{COURSE_CODE}}` - e.g., "BCOR 3750"
   - `{{COURSE_NAME}}` - e.g., "Strategic Management"
   - `{{SEMESTER}}` - e.g., "Fall 2025"
   - Course details, schedule, grading, policies

4. Add a header image to `images/header.jpg`

### Study Guides (`interviews/`)

1. Copy the appropriate template
2. Replace placeholders with your course content
3. Add your specific topics, concepts, and frameworks
4. Update sample questions to match your interview style

### Project Documentation (`project/`)

1. Define your project requirements in `requirements.md`
2. Break down milestones in `milestones.md`
3. Customize rubrics and evaluation criteria
4. Add any templates students will need

### Custom GPTs (`gpts/`)

1. Edit `instructions.md` with your course specifics
2. Review `ui-config.md` for recommended settings
3. Add course files to `knowledge/` directories
4. Create GPTs at https://chat.openai.com/gpts/editor
5. Test thoroughly before sharing with students

## Deployment

### GitHub Pages

1. Go to repository Settings → Pages
2. Set Source to "GitHub Actions"
3. The `pages.yml` workflow will deploy automatically
4. Access at `https://YOUR_USERNAME.github.io/syllabus/`

### Custom Domain (Optional)

1. Add a `CNAME` file with your domain
2. Configure DNS with your provider
3. Enable HTTPS in GitHub Pages settings

## Best Practices

### For Syllabi
- Keep content current and accurate
- Use clear, student-friendly language
- Include all required institutional policies
- Test print functionality before semester starts

### For Study Guides
- Update after each major topic is covered
- Include both recall and application questions
- Provide clear evaluation criteria
- Align with actual interview format

### For GPTs
- Test with various student scenarios
- Update when course content changes
- Monitor for appropriate responses
- Gather student feedback for improvement

## Contributing

If you improve this template, consider sharing your enhancements:

1. Fork the repository
2. Make your changes
3. Submit a pull request

## License

MIT License - See [LICENSE](LICENSE) for details.

---

*Template created for educational use. Customize freely for your courses.*
