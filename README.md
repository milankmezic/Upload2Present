# U2P - Upload to Present — Streamlit Cloud Edition

A fully in-memory file-to-PowerPoint converter that runs on Streamlit Community Cloud. No disk writes, no cloud storage—everything stays in RAM.

## Features

- **In-Memory Processing**: All files stored in `st.session_state` only
- **Multi-Format Support**: Images, videos, PDFs, documents, anything
- **Smart PowerPoint Generation**: 
  - Images become individual slides
  - Non-images listed on summary slide
- **Download Options**: PPTX deck + optional ZIP of originals
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
4. **Download**: Get your PowerPoint deck and/or ZIP of originals

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

## Memory Considerations

Streamlit Cloud has memory limits (~1GB). For large batches:
- Monitor file sizes in the UI
- Consider breaking into smaller batches
- Files are automatically cleared when you start a new batch

## License

This project is licensed under the GNU Affero General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

The GNU AGPL v3 is a copyleft license that ensures:
- Freedom to use, modify, and distribute the software
- Source code must be made available when the software is used over a network
- Any modifications must also be licensed under the same terms

For more information about the GNU AGPL v3, visit: https://www.gnu.org/licenses/agpl-3.0.html
