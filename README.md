# Volume Set Manager

A web-based tool for managing ISBN sets and generating formatted CSV output for volume sets. The application is available in both React and vanilla JavaScript implementations.

## Features

- ISBN-13 validation with checksum verification
- Dynamic volume entry management
- CSV generation in specified format
- Error handling and validation
- Form reset functionality

## ISBN Validation

The application implements ISBN-13 validation that includes:
- Format verification (13 digits)
- Checksum calculation and verification
- Handling of hyphens and spaces in input

### Validation Algorithm

The ISBN-13 checksum validation works as follows:
1. Removes all hyphens and spaces from the input
2. Verifies the input contains exactly 13 digits
3. Calculates the checksum using the ISBN-13 algorithm:
   - Multiply each digit alternately by 1 and 3
   - Sum the results
   - Calculate check digit as `(10 - (sum mod 10)) mod 10`
4. Verifies the calculated check digit matches the last digit of the ISBN

## CSV Output Format

The generated CSV follows this structure:
```
ISBN,NEW,[setISBN],[setDescription],,,,,,,,,N,,,,,,,,,,,,[volumeISBNs]
```

Where:
- `[setISBN]` is the validated ISBN-13 for the set
- `[setDescription]` is the user-provided description
- `[volumeISBNs]` are the validated volume ISBNs joined with semicolons

## File Naming

Generated CSV files follow the naming convention:
```
[timestamp]_[setISBN]_2.csv
```

## Input Requirements

1. Set ISBN:
   - Must be a valid ISBN-13 number
   - Spaces and hyphens are allowed in input

2. Set Description:
   - Required field
   - Cannot be empty

3. Volume ISBNs:
   - At least one volume ISBN required
   - Each must be a valid ISBN-13 number
   - Multiple volumes supported

## Error Handling

The application validates:
1. Set ISBN format and checksum
2. Presence of set description
3. Presence of at least one volume ISBN
4. Format and checksum of all volume ISBNs

## Implementations

### React Version
- Uses React state management
- Built with shadcn/ui components
- Requires React environment

### Vanilla JavaScript Version
- Single HTML file
- No external dependencies
- Can be run directly in browser
- Built with native HTML elements and JavaScript

## Setup and Usage

### React Version
1. Ensure React environment is set up
2. Import and use the `VolumeSetManager` component
3. Requires shadcn/ui components

### Vanilla Version
1. Save the HTML file
2. Open directly in a web browser
3. No installation or setup required

## User Interface Features

1. Dynamic Volume Management:
   - Add new volume inputs
   - Remove individual volumes
   - At least one volume input maintained

2. Form Controls:
   - Generate CSV button for output
   - Reset button to clear all inputs
   - Add Volume button for new entries

3. Visual Feedback:
   - Error messages for invalid inputs
   - Clear error display
   - Responsive design

## Browser Compatibility

The application uses standard web APIs and should work in all modern browsers that support:
- ES6+ JavaScript
- Blob API
- File download via anchor tags
