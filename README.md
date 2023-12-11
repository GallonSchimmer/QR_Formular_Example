# QR_Formular_Example

# Umfrageformular für LimeSurvey

This repository contains a simple survey form for LimeSurvey, featuring QR code generation and display functionality. The form is designed using HTML, CSS, and JavaScript.

## Usage Instructions

1. Fill in the Umfrage-ID and Matrikel fields in the open form.
2. Choose your preferred language from the dropdown menu.
3. Enter the title of the survey.
4. Click the "QR-Codes generieren" button.
5. The generated QR codes will appear on a new page under the text "Einladung zur Studie [Survey Title]" with the TU Berlin and Audiokommunikation logo.

## Setting up with Apache Webserver

To deploy this form using Apache:

1. Install Apache on your server if not already installed.
2. Place the HTML file in the appropriate directory, usually in the `htdocs` or `www` directory.
3. Access the form through your web browser using the server's address.

## Code Structure

### HTML (index.html)

- **Head Section:** Contains meta tags for character set, compatibility, and viewport settings.
- **CSS Styling:** Custom styling for body, headers, usage instructions, and form elements.
- **Body Section:** Includes the form and JavaScript section.

### CSS (style.css)

- **Styles for Body:** Sets the font-family and margin for the body.
- **Header Styles:** Aligns headers to the center.
- **Form Styles:** Sets styling for labels, input fields, dropdowns, and buttons.

### JavaScript (script.js)

- **generateQR Function:** Fetches input values, validates the Umfrage-ID and Matrikel fields, constructs a URL, and opens a new window to display the generated QR code.

## Examples

### HTML Example

```html
<!-- Input field for Matrikel number -->
<label for="matrikel">Matrikel:</label>
<input type="text" id="matrikel" name="matrikel" required>
```

### CSS Example

```css
/* Styles for Body */
body {
    font-family: 'Arial', sans-serif;
    margin: 20px;
}
```

### JavaScript Example

```javascript
// Function to generate QR codes
function generateQR() {
    // Get values from input fields
    var matrikel = document.getElementById("matrikel").value;
    var umfrageId = document.getElementById("umfrageId").value;

    // Check if Umfrage-ID and Matrikel fields are not empty
    if (umfrageId.trim() === "" || matrikel.trim() === "") {
        alert("Umfrage-ID und Matrikel dürfen nicht leer sein.");
        return;
    }

  // Construct the complete URL for generating QR code
  var qrUrl = "student-surveys.ak.tu-berlin.de/index.php/" + umfrageId + "?lang=" + sprache + "&matrikel=" + matrikel;
			
            // Open a new window to display the generated QR code with logo
            var newWindow = window.open();
}
```

## Validation and Security

Validation is performed to ensure that the Umfrage-ID and Matrikel fields are not empty. Additional security measures, such as input sanitization, can be implemented on the server-side to prevent potential vulnerabilities.

Feel free to enhance security features based on specific requirements and use cases.
