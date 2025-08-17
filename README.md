# U2P - Upload to Present — Streamlit Cloud Edition

A fully in-memory file-to-PowerPoint converter that runs on Streamlit Community Cloud. No disk writes, no cloud storage—everything stays in RAM.

## 🚀 Live Demo

**Test the app online**: [https://upload2present.streamlit.app/](https://upload2present.streamlit.app/)

Upload files, organize them, and download your PowerPoint presentation instantly!

## Features

- **In-Memory Processing**: All files stored in `st.session_state` only
- **Multi-Format Support**: Images, videos, PDFs, documents, anything
- **Smart PowerPoint Generation**: 
  - Images become individual slides
  - Non-images listed on summary slide
- **Download Options**: PPTX deck + PDF document + ZIP of originals
- **Cloud-Ready**: Minimal dependencies, perfect for Streamlit Cloud

## Quick Deploy

1. **Fork/Clone** this repo to your GitHub
2. **Deploy to Streamlit Cloud**:
   - Go to [share.streamlit.io](https://share.streamlit.io)
   - Connect your GitHub repo
   - Set main file path: `app.py`
   - Deploy!

## Local Development

```bash
# Clone and setup
git clone <your-repo>
cd deckify-streamlit-cloud

# Create virtual environment
python -m venv .venv

# Activate (Windows)
.venv\Scripts\activate
# OR Activate (Mac/Linux)
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run locally
streamlit run app.py
```

## How It Works

1. **Upload Files**: Drag & drop multiple files of any type
2. **Add to Batch**: Files are stored in memory with metadata
3. **Build PPTX**: Images become slides, others get listed
4. **Download**: Get your PowerPoint deck, PDF document, and/or ZIP of originals

## File Structure

```
u2p-streamlit-cloud/
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
└── README.md          # This file
```

## Dependencies

- `streamlit` - Web framework
- `python-pptx` - PowerPoint generation
- `Pillow` - Image processing
- `PyMuPDF` - PDF processing
- `exifread` - EXIF metadata extraction
- `reportlab` - PDF generation

## Memory Considerations

Streamlit Cloud has memory limits (~1GB). For large batches:
- Monitor file sizes in the UI
- Consider breaking into smaller batches
- Files are automatically cleared when you start a new batch

## 🔒 Security Features

### Data Privacy & Security
- **In-Memory Only**: All files are stored exclusively in Streamlit's session state (RAM)
- **No Persistent Storage**: Files are never written to disk or cloud storage
- **Automatic Cleanup**: Data is automatically cleared when:
  - Starting a new batch
  - Refreshing the browser
  - Closing the browser tab
  - Session timeout (typically 30 minutes)

### File Processing Security
- **No File System Access**: The app cannot read from or write to your local file system
- **Isolated Processing**: Each file is processed in memory without external dependencies
- **No Network Transfers**: Files are not sent to external services or APIs
- **Metadata Extraction**: Only basic file metadata and EXIF data (for images) are extracted

### Privacy Protection
- **No Logging**: File contents are not logged or stored anywhere
- **No Analytics**: No tracking of uploaded files or user behavior
- **Session Isolation**: Each browser session is completely isolated
- **No Cross-Session Data**: Files from one session cannot be accessed from another

### Limitations & Considerations
- **Public Deployment**: The live demo is publicly accessible - don't upload sensitive documents
- **Memory Limits**: Large files may cause memory issues or app crashes
- **Session Timeout**: Files will be lost if the session expires
- **Browser Security**: Relies on browser security for file upload handling

### Best Practices
- **Test with Non-Sensitive Files**: Use sample documents for testing
- **Monitor File Sizes**: Keep individual files under 50MB for best performance
- **Use Local Deployment**: For sensitive documents, deploy locally or on private infrastructure
- **Clear Browser Data**: Clear browser cache/cookies after use if concerned about privacy

## License

This project is licensed under the GNU Affero General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

The GNU AGPL v3 is a copyleft license that ensures:
- Freedom to use, modify, and distribute the software
- Source code must be made available when the software is used over a network
- Any modifications must also be licensed under the same terms

For more information about the GNU AGPL v3, visit: https://www.gnu.org/licenses/agpl-3.0.html
