# Volume Set Manager

A web-based tool for managing book volume sets and generating formatted CSV files for bulk operations.

## Features

### ISBN Management
- Validates 13-digit ISBNs for both sets and individual volumes
- Automatically calculates and verifies ISBN checksums
- Strips spaces and hyphens from ISBNs for standardization

### Description Handling
- Enforces 58-character limit for both set and volume descriptions
- Real-time character counting for all description fields
- Visual feedback when approaching or exceeding character limits
- Automatic trimming of whitespace

### Volume Management
- Add/remove volumes dynamically
- Each volume requires both ISBN and description
- No limit on the number of volumes per set
- Real-time validation of all volume data

### Excel Import
- Import data from Excel files (.xlsx, .xls)
- Template available for download
- Validates all data during import:
  - Set ISBN format and checksum
  - Set description length (max 58 characters)
  - Volume ISBN formats and checksums
  - Volume description lengths (max 58 characters)
- Detailed error reporting for invalid entries

### CSV Generation
- Generates standardized CSV format for bulk operations
- File naming convention: timestamp_setISBN_2.csv
- CSV Structure:
  - Volume rows listed first
  - Set row with all volume ISBNs at the end
  - Includes necessary formatting and placeholders

### Data Validation
- Real-time validation of all inputs
- Checks for:
  - Valid ISBN-13 numbers
  - Description length limits (58 characters)
  - Required fields
  - Proper data formatting
- Clear error messages for validation failures

### User Interface
- Clean, intuitive Bootstrap-based interface
- Responsive design
- Visual feedback for all operations
- Error alerts with specific messages
- Loading indicators for file operations

## Excel Template Format
1. Row 1: Headers (ISBN, Description)
2. Row 2: Set ISBN and Description
3. Row 3+: Volume ISBNs and Descriptions

## CSV Output Format
The tool generates a CSV file with the following structure:
```
ISBN,NEW,[VolumeISBN],[VolumeDescription],,,,,,,,,N,,,,,,,,,,,
ISBN,NEW,[SetISBN],[SetDescription],,,,,,,,,N,,,,,,,,,,,,[Volume1ISBN;Volume2ISBN;...]
```

## Error Handling
- Invalid ISBN format or checksum
- Description length exceeding 58 characters
- Missing required fields
- Invalid Excel file format
- Invalid data in Excel file
- File processing errors

## Browser Compatibility
- Works with modern web browsers
- Requires JavaScript enabled
- Supports file download functionality
- Handles local file processing

## Dependencies
- Bootstrap 5.3.2
- Bootstrap Icons 1.11.3
- SheetJS 0.18.5
- Modern web browser with JavaScript enabled

## Usage Instructions

### Manual Entry Method
1. Enter set ISBN (13 digits) and description (max 58 characters)
2. Add volumes using the "Add Volume" button
3. For each volume:
   - Enter 13-digit ISBN
   - Enter description (max 58 characters)
4. Click "Generate CSV" to create and download the formatted file
5. Use "Reset" to clear all fields

### Excel Import Method
1. Download the Excel template
2. Fill in your data following the template format
3. Import the Excel file
4. Review and modify imported data if needed
5. Generate CSV

## Notes
- All ISBNs must be valid 13-digit numbers with correct checksums
- Descriptions are limited to 58 characters including spaces
- At least one volume is required to generate a CSV
- The tool provides real-time validation and feedback
- All data is processed locally in the browser
- Generated CSV files include a timestamp in the filename for tracking
- Excel template follows a specific format that must be maintained for successful imports