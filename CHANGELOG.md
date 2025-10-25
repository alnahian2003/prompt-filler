# Changelog

All notable changes to Prompt Filler will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.1.0] - 2025-10-25

### 🎨 UI/UX Improvements

#### Enhanced
- **Toast notifications** now feature improved backdrop filters with enhanced blur and saturation for better visibility
- **Preview empty state** reduced vertical height for more compact UI (min-height reduced from 10rem to 6rem)
- **Icon containers** in preview empty state are now perfect circles with consistent dimensions
- **Button tooltips** completely redesigned with custom CSS tooltips featuring:
  - Dark/light mode support with theme-aware backgrounds
  - Keyboard shortcut indicators (e.g., "⌘/Ctrl+S", "⌘/Ctrl+Shift+C")
  - Smooth fade-in animations
  - Clean, modern design matching the overall aesthetic
- **Token tooltips** in preview use native browser tooltips for better performance

#### Removed
- **Progress bar** completely removed for cleaner, simpler interface
- **Custom CSS** minimized in favor of Tailwind utility classes where possible

### ✨ Features

#### Smart Label Formatting
- Automatically converts placeholder naming conventions to human-readable labels:
  - `[sender_name]` → "Sender Name"
  - `[sender-name]` → "Sender Name"
  - `[senderName]` → "Sender Name"
- Uses Tailwind's `capitalize` utility for proper title casing

#### Interactive Preview
- **Click-to-edit tokens**: Click any highlighted token in the preview to jump directly to its input field
- Instant preview updates when loading from local storage

#### Keyboard Shortcuts
- **Save to Local Storage**: `Ctrl/Cmd + S`
- **Copy Filled Prompt**: `Ctrl/Cmd + Shift + C`
- **Load from Local Storage**: `Ctrl/Cmd + Shift + V`
- **Clear All**: `Ctrl/Cmd + Shift + X`

All shortcuts now implemented using native Alpine.js `@keydown.window` directives for better maintainability.

#### Realistic Example Data
- Completely redesigned example data filling system with:
  - 24+ data categories including names, contacts, organizations, roles, temporal data, metrics, locations, marketing, and more
  - Smart pattern matching that prioritizes specific patterns over general ones
  - Data-driven architecture using flat `MATCH_RULES` array
  - Hierarchical matching (e.g., "first_name" → first names, "last_name" → last names, "name" → full names)

### 🔧 Technical Improvements

#### Alpine.js Migration
- **Toast system** converted from vanilla JavaScript DOM manipulation to Alpine.js reactive state
  - Uses `toastMessage`, `toastVisible`, `toastClasses` reactive properties
  - Implements `x-show`, `x-transition`, and `:class` bindings
- **Keyboard shortcuts** migrated from `addEventListener` to Alpine.js `@keydown.window` modifiers
- Minimized vanilla JavaScript in favor of declarative Alpine.js patterns

#### Code Quality
- **Zero if-blocks** in `fillExample()` function:
  - Replaced ~25 nested if-blocks with clean data-driven approach
  - Uses `Array.find()` and ternary operators instead of imperative conditionals
  - Easy to extend with new data patterns
- **Consistent button styling**: All secondary action buttons now use neutral border style for visual hierarchy
- **DRY principles**: Eliminated code repetition throughout the codebase

### 🐛 Bug Fixes
- Fixed `loadFromLocal()` not updating preview instantly (now calls `parse()` after loading)
- Fixed quick-copy button styling inconsistencies
- Fixed tooltip conflicts between custom button tooltips and native token tooltips

### 📚 Documentation
- Updated README with new features:
  - Smart label formatting examples
  - Interactive preview features
  - Complete keyboard shortcuts reference
  - Enhanced "How it works" section

---

## [1.0.0] - Initial Release

### Features
- AI prompt template management with dynamic placeholder detection
- Real-time preview with syntax highlighting
- Export filled prompts as JSON
- Copy to clipboard functionality
- Local storage persistence
- Responsive design with dark/light mode support
- Built with Alpine.js and Tailwind CSS

