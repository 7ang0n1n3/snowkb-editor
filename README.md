# ServiceNow KB Offline Editor

A powerful offline Knowledge Base editor for ServiceNow, built with TinyMCE WYSIWYG editor. Create, edit, and manage KB articles without requiring a ServiceNow instance.

![Version](https://img.shields.io/badge/version-4.5-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![TinyMCE](https://img.shields.io/badge/TinyMCE-6.x-orange.svg)

## 🚀 Features

### ✨ Rich Text Editing
- **WYSIWYG Editor**: Full-featured TinyMCE editor with intuitive interface
- **Text Formatting**: Bold, italic, underline, font family, size, and color controls
- **Layout Tools**: Text alignment, lists, tables, and page breaks
- **Advanced Features**: Links, images, full-screen mode, and source code view
- **Auto-save**: Debounced auto-save (1 second after last edit) with visual indicators
- **Keyboard Shortcut**: `Ctrl+S` / `Cmd+S` saves the current article and captures a version snapshot

### 📝 Article Management
- **Create Articles**: Generate new KB articles with auto-assigned template IDs (UUID)
- **Metadata Support**: Title, category, status, and short description fields
- **Custom Categories**: Add and remove categories on the fly; built-in defaults are protected
- **Status Tracking**: Draft, Ready for Review, and Authorized Usage states
- **Search & Filter**: Debounced search through article titles and descriptions
- **Delete Articles**: Remove articles with confirmation dialog; version history is pruned automatically
- **Version History**: Up to 5 snapshots per article captured on every manual save; browse and restore from the History modal

### 💾 Data Management
- **Local Storage**: All data saved in browser localStorage with quota-exceeded alerting
- **Import/Export**: JSON-based import and export functionality
- **Export Current Article**: Download only the open article as a named JSON file
- **Duplicate Prevention**: Smart merging when importing existing articles
- **Import Validation**: Malformed or invalid entries are detected and skipped during import
- **Import Sanitization**: `<script>` tags, inline event handlers, and `javascript:` hrefs are stripped from imported content
- **Backup Support**: Export all articles for backup purposes

### 🎨 User Interface
- **Modern Design**: Clean, responsive interface with gradient background
- **Responsive Editor**: TinyMCE scales to container width on all screen sizes
- **Dynamic Sidebar**: Article list height adapts to the browser window
- **Dark/Light Theme**: Toggle between dark and light themes; current article is saved before reinit
- **Sidebar Navigation**: Easy article browsing and management
- **Status Indicators**: Visual badges showing article status
- **Search Functionality**: Debounced real-time search through article list

## 📋 Requirements

- Modern web browser with localStorage support
- No internet connection required (fully offline)
- No server setup needed

## 🛠️ Installation

1. **Download**: Clone or download this repository
2. **Extract**: Unzip the files to your desired location
3. **Open**: Open `index.html` in your web browser
4. **Start Editing**: Begin creating your Knowledge Base articles

## 📖 Usage

### Creating a New Article

1. Click the **"Create New Article"** button in the sidebar
2. Fill in the metadata fields:
   - **Title**: Enter the article title
   - **Category**: Select from the list, or click **+** to add a custom category
   - **Status**: Choose Draft, Ready for Review, or Authorized Usage
   - **Short Description**: Provide a brief summary (max 255 characters)
3. Use the TinyMCE editor to create your content
4. Content is automatically saved as you type

### Managing Articles

- **View Articles**: Click on any article in the sidebar to load it
- **Search**: Use the search box to find specific articles
- **Edit**: Make changes in the editor — auto-save and `Ctrl+S` / `Cmd+S` are both available
- **Delete**: Click the "Delete" button to remove an article
- **Version History**: Click the **"History"** button in the toolbar to view and restore past versions
- **Theme Toggle**: Click the moon/sun icon in the top-right to switch between dark and light themes

### Categories

- **Built-in categories**: Procedures, Policies, Troubleshooting
- **Add a category**: Click the **+** button next to the Category field and enter a name
- **Remove a category**: Select it from the dropdown and click **−** (built-in categories are protected)
- Custom categories persist across sessions in localStorage

### Import/Export

#### Exporting All Articles
1. Click the **"Save JSON"** button in the header
2. Choose a location to save the JSON file
3. File will be named with current date: `servicenow-kb-articles-YYYY-MM-DD.json`

#### Exporting a Single Article
1. Open the article you want to export
2. Click the **"Export Article"** button in the toolbar
3. File will be named `{kbNumber}-{title}.json` and imports cleanly back in

#### Importing Articles
1. Click the **"Load JSON"** button in the header
2. Select a previously exported JSON file
3. Confirm the import to merge articles with existing ones
4. Duplicate articles (by ID) and malformed entries are automatically filtered
5. HTML content is sanitized on import (scripts and event handlers stripped)

## 🏗️ Project Structure

```
snowkb-editor/
├── index.html              # Main application file
├── libs/                   # Third-party libraries
│   └── tinymce/           # TinyMCE editor library
│       ├── tinymce.min.js # Core TinyMCE library
│       ├── plugins/       # TinyMCE plugins
│       ├── themes/        # Editor themes
│       └── skins/         # UI skins (including dark theme)
├── LICENSE                 # MIT License
└── README.md              # This file
```

## 🔧 Technical Details

### Dependencies
- **TinyMCE 6.x**: WYSIWYG editor with extensive plugin support

### Browser Compatibility
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

### Data Storage
- **Format**: JSON
- **Location**: Browser localStorage
- **Keys**: `servicenow-kb-articles` (articles), `servicenow-kb-categories` (custom categories), `servicenow-kb-history` (version snapshots), `theme` (dark/light preference)

### Article Schema
```json
{
  "id": "550e8400-e29b-41d4-a716-446655440000",
  "kbNumber": "TP0000000",
  "title": "Article Title",
  "category": "procedures|policies|troubleshooting",
  "status": "draft|review|published",
  "shortDescription": "Brief description",
  "content": "HTML content from TinyMCE",
  "createdAt": 1234567890,
  "updatedAt": 1234567890
}
```

## 🎯 Use Cases

- **Content Creation**: Write KB articles offline before publishing to ServiceNow
- **Content Review**: Edit and review articles with team members
- **Backup Management**: Export articles for backup and version control
- **Training**: Use for training purposes without affecting production data
- **Migration**: Prepare content for migration to ServiceNow

## 🔮 Future Enhancements

- [x] Dark/Light theme toggle
- [x] Custom categories (add/remove with persistence)
- [x] Export single article
- [x] Keyboard shortcut (`Ctrl+S`) to save
- [x] Import sanitization (scripts/event handlers stripped)
- [x] Version history and tracking (per-article snapshots, restore, max 5)
- [ ] PDF export functionality
- [ ] Template system for common article types
- [ ] Image upload and management
- [ ] Collaborative editing features
- [ ] Bulk operations (import/export multiple files)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For issues, questions, or feature requests:
1. Check the existing issues in the repository
2. Create a new issue with detailed information
3. Include browser version and steps to reproduce

## 🙏 Acknowledgments

- **TinyMCE Team**: For the excellent WYSIWYG editor
- **ServiceNow Community**: For inspiration and feedback

---

**Version**: 4.5
**Last Updated**: 2026
**Maintainer**: 7ANG0N1N3