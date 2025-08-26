# Recipe Converter

A simple, web-based tool for scaling recipe measurements. Convert recipe amounts by multiplying them with custom scaling factors - perfect for halving recipes, doubling servings, or adjusting for any portion size.

## Features

- **Flexible Input**: Accepts decimal numbers (0.5, 1.25) and fractions (1/2, 3/4, 1/3)
- **Multiple Measurement Types**: Supports volume, weight, and specialty cooking measurements
- **Smart Output Formatting**: Displays results as easy-to-read fractions when possible, falls back to decimals for complex values
- **Clean Interface**: Simple, centered design with intuitive controls

## Supported Measurements

### Volume
- Cup, Tablespoon, Teaspoon, Fluid Ounce, Milliliter, Liter

### Weight  
- Ounce, Pound, Gram, Kilogram

### Other
- Pinch, Dash

## Usage

1. Enter the original measurement amount (e.g., `1.5` or `1 1/2`)
2. Select the measurement unit from the dropdown
3. Enter the scaling factor (e.g., `0.5` to halve, `2` to double)
4. Click "Calculate" to see the scaled result

### Example
- Original: `2 cups`
- Multiply by: `0.5` 
- Result: `1 cup`

## Technical Implementation

### Architecture Choices

**Single-Page Application**: Built as a self-contained HTML file with embedded CSS and JavaScript for maximum portability and ease of deployment. No external dependencies or build process required.

**Client-Side Processing**: All calculations happen in the browser using JavaScript, eliminating server dependencies and providing instant results without network requests.

### User Interface Design

**Responsive Layout**: Uses CSS Flexbox for consistent centering and responsive behavior across different screen sizes. The container adapts from 400px max-width down to mobile dimensions.

**Visual Hierarchy**: Gradient background provides visual appeal while maintaining focus on the white container. Input sections use subtle background colors to group related controls without overwhelming the interface.

**Accessibility Considerations**: 
- Semantic HTML structure with proper labels
- Keyboard navigation support (Enter key triggers calculation)
- Sufficient color contrast ratios
- Focus states for interactive elements

### Fraction Processing

**Input Parsing**: Custom `parseNumber()` function handles both decimal and fraction inputs by detecting the '/' character and performing division. This allows users to enter measurements in their preferred format.

**Output Formatting**: The `formatResult()` function converts decimal results back to common fractions (1/2, 1/4, 3/4, etc.) when possible, using a tolerance-based matching system. This improves readability for cooking measurements where fractions are more intuitive than decimals.

**Fraction Mapping**: Predefined fraction dictionary covers the most common cooking fractions:
- Basic halves and quarters: 1/2, 1/4, 3/4
- Thirds: 1/3, 2/3  
- Eighths: 1/8, 3/8, 5/8, 7/8
- Sixths: 1/6, 5/6

### Input Validation

**Graceful Error Handling**: The application validates required fields and provides clear feedback messages without breaking functionality. Invalid inputs default to zero rather than causing JavaScript errors.

**Flexible Number Recognition**: Accepts various input formats including integers, decimals, and fractions, making the tool adaptable to different user preferences and recipe formats.

### Performance Considerations

**Minimal Resource Usage**: Lightweight implementation with no external libraries or frameworks. Total file size under 10KB ensures fast loading even on slow connections.

**Efficient DOM Manipulation**: Direct element selection and value updates minimize browser reflow and maintain smooth performance.

## Browser Compatibility

- Modern browsers supporting ES6+ (Chrome 60+, Firefox 55+, Safari 12+, Edge 79+)
- No polyfills required for core functionality
- Graceful degradation on older browsers

## File Structure

```
recipe-converter.html
├── HTML structure
├── Embedded CSS styles
└── JavaScript functionality
```

## Future Enhancements

Potential improvements for future versions:
- Temperature conversion (Fahrenheit/Celsius)
- Imperial/Metric system conversion
- Recipe saving and management
- Mobile app version
- Bulk ingredient processing

## License

Open source project. Feel free to modify and distribute as needed.
