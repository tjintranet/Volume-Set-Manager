# Volume Set Manager

A web-based application for managing ISBN sets and generating formatted CSV output. This tool allows users to create and manage volume sets with ISBN-13 validation and supports both manual entry and Excel file import.

## Features

- ISBN-13 validation with checksum verification
- Excel file import functionality
- CSV generation in specified format
- Dynamic volume entry management
- Form reset functionality
- Template download option
- Comprehensive error handling

## Installation

1. Save the HTML file to your local machine
2. Open the file in a web browser
3. No additional installation or setup required

## Usage

### Manual Entry

1. Enter the Set ISBN (13-digit ISBN required)
2. Enter the Set Description
3. Add Volume ISBNs using the "Add Volume" button
4. Click "Generate CSV" to create and download the formatted CSV file

### Excel Import

1. Click "Download Excel Template" to get the template file
2. Fill out the template following the format:
   - Row 1: Headers (ISBN, Description)
   - Row 2: Set ISBN and Description
   - Row 3+: Volume ISBNs and Descriptions
3. Click "Import from Excel" and select your filled template
4. Verify the imported data
5. Click "Generate CSV" to generate the output file

### Reset Form

- Click the "Reset" button to clear all entries and start over

## Input Validation

### ISBN Validation
- Validates ISBN-13 format
- Performs checksum verification
- Handles spaces and hyphens in input
- Validates both set ISBN and volume ISBNs

### Excel File Validation
- Validates file format
- Checks for required headers
- Validates all ISBNs before import
- Provides specific error messages for invalid entries

## CSV Output Format

The generated CSV follows this structure:
```
ISBN,NEW,[setISBN],[setDescription],,,,,,,,,N,,,,,,,,,,,,,{volumeISBNs}
```

Where:
- `[setISBN]` is the validated ISBN-13 for the set
- `[setDescription]` is the user-provided description
- `[volumeISBNs]` are the validated volume ISBNs joined with semicolons

## File Naming Convention

Generated files follow the format:
```
[timestamp]_[setISBN]_2.csv
```

## Error Handling

The application handles various error cases including:
- Invalid ISBN formats
- Missing required fields
- Invalid Excel file format
- Missing or invalid volume ISBNs
- File processing errors

## Technical Details

### Dependencies
- XLSX.js (for Excel file processing)
- No other external dependencies required

### Browser Support
- Works in all modern browsers
- Requires JavaScript enabled
- Requires File API support

## Limitations

- Only supports ISBN-13 format
- Excel files must follow the exact template format
- All ISBNs must be valid for CSV generation
- No support for offline operation
- Single file per operation

## Troubleshooting

Common issues and solutions:

1. **File Won't Import**
   - Ensure file follows template format
   - Check that all ISBNs are valid
   - Verify file is in .xlsx or .xls format

2. **Invalid ISBN Errors**
   - Verify ISBN is 13 digits
   - Check for correct checksum
   - Remove any special characters

3. **CSV Not Generating**
   - Ensure all required fields are filled
   - Verify all ISBNs are valid
   - Check for error messages

## Contributing

Feel free to submit issues and enhancement requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.