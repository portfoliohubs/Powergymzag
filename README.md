# Gym Training System - Hugo Static Site

A production-ready static gym training website built with Hugo, featuring smart UI/UX, gender-specific filtering, and comprehensive exercise management.

## 🚀 Features

- **Smart UI/UX**: Modern, responsive design with smooth animations
- **Gender Filtering**: Male/Female exercise differentiation
- **Theme Toggle**: Dark/Light mode with localStorage persistence
- **Equipment Categories**: Free Weights, Machines, Cables
- **Training Programs**: Push/Pull/Legs and Smart Body Parts
- **Image Management**: Centralized image configuration via config.toml
- **Fully Static**: GitHub Pages compatible, no backend required

## 📁 Project Structure

```
├── .github/workflows/
│   └── deploy.yml          # GitHub Pages deployment
├── content/
│   ├── push.md             # Push training program
│   ├── pull.md             # Pull training program
│   ├── legs.md             # Legs training program
│   ├── chest.md            # Chest training program
│   ├── back.md             # Back training program
│   ├── shoulders.md        # Shoulders training program
│   ├── arms.md             # Arms training program
│   ├── core.md             # Core training program
│   ├── barbell-bench-press.md
│   ├── dumbbell-fly.md
│   ├── cable-fly.md
│   ├── machine-chest-press.md
│   ├── pull-ups.md
│   ├── bent-over-rows.md
│   ├── squats.md
│   ├── overhead-press.md
│   ├── bicep-curls.md
│   └── planks.md
├── layouts/_default/
│   └── single.html         # Single page template
├── config.toml             # Site configuration and images
├── index.html              # Homepage with hero section
└── README.md               # This file
```

## 🛠️ Configuration

All site content is managed through `config.toml`:

- **Gym Information**: Name, slogan, default theme/gender
- **Images**: Centralized image URLs for all exercises
- **Training Programs**: Structure and descriptions

## 🏋️ Exercise Categories

### Training Programs
- **Push/Pull/Legs**: Classic 3-day split
- **Smart Body Parts**: Targeted muscle group training

### Equipment Types
- **Free Weights**: Barbells, dumbbells
- **Machines**: Guided movement machines
- **Cables**: Constant resistance exercises

### Muscle Groups
- Chest, Back, Shoulders, Arms, Legs, Core

## 🎨 UI Features

### Theme System
- Light/Dark mode toggle
- Persistent user preferences
- Smooth transitions

### Gender Filtering
- Male/Female exercise filtering
- Dynamic content display
- Gender-specific imagery when available

### Responsive Design
- Mobile-first approach
- Tablet and desktop optimizations
- Touch-friendly interface

## 🚀 Deployment

### GitHub Pages Setup

1. **Repository Settings**:
   - Go to Settings → Pages
   - Source: GitHub Actions

2. **Push to Main**:
   - The workflow will automatically build and deploy
   - Site will be available at `https://username.github.io/repository-name`

### Local Development

1. **Install Hugo**:
   ```bash
   # macOS
   brew install hugo
   
   # Windows
   choco install hugo
   
   # Linux
   sudo apt install hugo
   ```

2. **Run Development Server**:
   ```bash
   hugo server -D
   ```

3. **Build for Production**:
   ```bash
   hugo --minify
   ```

## 📝 Adding New Exercises

1. Create new markdown file in `/content/`
2. Add front matter with required fields:
   ```yaml
   ---
   title: "Exercise Name"
   type: "exercise"
   train_type: "push|pull|legs|core"
   muscle: "chest|back|shoulders|arms|legs|core"
   equipment: "free_weights|machines|cables"
   gender: ["male", "female"]
   difficulty: "beginner|intermediate|advanced"
   exercise_name: "slug_for_image"
   ---
   ```

3. Add exercise description in markdown body
4. Add image URL to `config.toml` under appropriate muscle section

## 🖼️ Image Management

Images are managed centrally in `config.toml`:

```toml
[images]
  [images.chest]
    barbell_bench_press = "https://example.com/image.jpg"
    dumbbell_fly = "https://example.com/image2.jpg"
```

The template automatically resolves images based on:
- Exercise slug (from `exercise_name` field)
- Muscle group
- Gender (if gender-specific images are available)

## 🎯 Customization

### Site Branding
Edit `config.toml`:
- `gym_name`: Your gym name
- `slogan`: Motivational slogan
- `default_theme`: "light" or "dark"
- `default_gender`: "male" or "female"

### Styling
All styles are embedded in HTML templates:
- `index.html`: Homepage styles
- `layouts/_default/single.html`: Content page styles

### Colors
CSS variables in both templates:
- `--bg-primary`: Main background
- `--accent`: Primary color
- `--text-primary`: Main text color

## 🔧 Technical Details

- **Static Site Generator**: Hugo
- **No Frameworks**: Pure HTML, CSS, JavaScript
- **Deployment**: GitHub Pages via GitHub Actions
- **Storage**: localStorage for user preferences
- **Images**: External URLs (Unsplash examples provided)

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test locally with `hugo server`
5. Submit a pull request

## 📞 Support

For issues or questions:
1. Check existing GitHub Issues
2. Create a new issue with detailed description
3. Include screenshots if applicable

---

Built with ❤️ using Hugo and vanilla web technologies.
