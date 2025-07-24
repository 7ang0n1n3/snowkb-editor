# ServiceNow KB Offline Editor

A powerful offline Knowledge Base editor for ServiceNow, built with TinyMCE WYSIWYG editor. Create, edit, and manage KB articles without requiring a ServiceNow instance.

![Version](https://img.shields.io/badge/version-4.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![TinyMCE](https://img.shields.io/badge/TinyMCE-6.x-orange.svg)

## 🚀 Features

### ✨ Rich Text Editing
- **WYSIWYG Editor**: Full-featured TinyMCE editor with intuitive interface
- **Text Formatting**: Bold, italic, underline, font family, size, and color controls
- **Layout Tools**: Text alignment, lists, tables, and page breaks
- **Advanced Features**: Links, images, full-screen mode, and source code view
- **Auto-save**: Automatic saving with visual indicators

### 📝 Article Management
- **Create Articles**: Generate new KB articles with auto-assigned template IDs
- **Metadata Support**: Title, category, status, and short description fields
- **Status Tracking**: Draft, Ready for Review, and Authorized Usage states
- **Search & Filter**: Find articles by title or description
- **Delete Articles**: Remove articles with confirmation dialog

### 💾 Data Management
- **Local Storage**: All data saved in browser localStorage
- **Import/Export**: JSON-based import and export functionality
- **Duplicate Prevention**: Smart merging when importing existing articles
- **Backup Support**: Export all articles for backup purposes

### 🎨 User Interface
- **Modern Design**: Clean, responsive interface with gradient background
- **Dark/Light Theme**: Toggle between dark and light themes for comfortable editing
- **Sidebar Navigation**: Easy article browsing and management
- **Status Indicators**: Visual badges showing article status
- **Search Functionality**: Real-time search through article list

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
   - **Category**: Select from Procedures, Policies, or Troubleshooting
   - **Status**: Choose Draft, Ready for Review, or Authorized Usage
   - **Short Description**: Provide a brief summary (max 255 characters)
3. Use the TinyMCE editor to create your content
4. Content is automatically saved as you type

### Managing Articles

- **View Articles**: Click on any article in the sidebar to load it
- **Search**: Use the search box to find specific articles
- **Edit**: Make changes in the editor - auto-save is enabled
- **Delete**: Click the "Delete" button to remove an article
- **Theme Toggle**: Click the moon/sun icon in the top-right to switch between dark and light themes

### Import/Export

#### Exporting Articles
1. Click the **"Save"** button in the header
2. Choose a location to save the JSON file
3. File will be named with current date: `servicenow-kb-articles-YYYY-MM-DD.json`

#### Importing Articles
1. Click the **"Load"** button in the header
2. Select a previously exported JSON file
3. Confirm the import to merge articles with existing ones
4. Duplicate articles (by ID) will be automatically filtered

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
- **Key**: `servicenow-kb-articles`

### Article Schema
```json
{
  "id": "unique-article-id",
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
- [ ] PDF export functionality
- [ ] Template system for common article types
- [ ] Image upload and management
- [ ] Collaborative editing features
- [ ] Version history and tracking
- [ ] Custom categories and metadata fields
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

**Version**: 4.2  
**Last Updated**: 2025  
**Maintainer**: 7ANG0N1N3 