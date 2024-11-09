# DoclingBatch

# PDF Document Processor

A Google Colab script for batch processing PDF documents into multiple structured formats. This tool extracts and preserves document structure, making content easily accessible for further analysis or processing using the docling library.

## Features

- Batch processing of multiple PDF files
- Maintains document structure and formatting
- Multiple output formats:
  - Plain text (`.txt`)
  - Markdown (`.md`)
  - Structured JSON (`.json`)
  - Document tokens (`.doctags`)
- Table structure preservation
- Automatic zip file creation of all outputs
- No OCR by default (configurable)

## Requirements

- Google Colab account
- PDF files to process
- Python packages (automatically installed):
  - docling
  - poppler-utils
  - google-colab

## Usage

1. Open in Google Colab:
   - Create a new notebook
   - Copy the script into three separate cells as marked in the comments

2. Run the cells in order:
   ```python
   # First cell: Package installation
   # Second cell: Function definitions
   # Third cell: Main execution
   ```

3. When prompted, upload your PDF files
   - You can select multiple files at once
   - Files will be processed sequentially

4. Results:
   - View processed files in the scratch directory
   - See text and markdown output in the console
   - Download all outputs as a zip file

## Output Formats

- **Text (.txt)**: Clean, plain text extraction
- **Markdown (.md)**: Preserves headers, lists, and basic formatting
- **JSON (.json)**: Structured representation of the document
- **DocTags (.doctags)**: Document tokens for NLP/analysis

## Configuration

Modify `PdfPipelineOptions` in the main function to customize processing:

```python
pipeline_options = PdfPipelineOptions()
pipeline_options.do_ocr = False  # Enable/disable OCR
pipeline_options.do_table_structure = True  # Table detection
pipeline_options.table_structure_options.do_cell_matching = True
```

## Directory Structure

```
.
├── tests/
│   └── data/    # Uploaded PDF files
├── scratch/     # Processed outputs
└── output_files.zip  # Final compressed outputs
```

## Processing Flow

1. Create necessary directories
2. Upload PDF files
3. Process each file:
   - Convert to multiple formats
   - Save outputs to scratch directory
4. Display results
5. Create and download zip file

## Limitations

- Runs only in Google Colab environment
- OCR disabled by default
- Memory limitations based on Colab's resources
- Processing time varies with document size and complexity

## Contributing

Feel free to open issues or submit pull requests with improvements.

## License

This project is open source and available under the MIT License.
