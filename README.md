# Captcha Solver Web App

## Summary
This static web application provides a simple, client-side interface for solving captchas. It's designed to display a captcha image fetched from a user-provided URL and allow users to input their solution. The application measures and displays the time taken to solve the captcha, offering a straightforward tool for testing or individual captcha resolution.

## Setup
To get this application running locally, simply follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/your-username/captcha-solver-web-app.git
    cd captcha-solver-web-app
    ```
2.  **Open in Browser:**
    Open the `index.html` file directly in your preferred web browser. You can do this by navigating to the file path (e.g., `file:///path/to/your/repo/index.html`) or by using a local web server (e.g., `python -m http.server` from the repository root, then navigating to `http://localhost:8000/index.html`).

## Usage
The application is designed to receive the captcha image URL via a query parameter.

1.  **Load the Application with a Captcha URL:**
    Append `?url=` followed by the full URL of the captcha image to your browser's address bar.
    **Example:**
    `file:///path/to/your/repo/index.html?url=https://www.example.com/path/to/your/captcha.png`
    (Replace `https://www.example.com/path/to/your/captcha.png` with an actual direct link to a captcha image.)

    *Note: Due to browser security policies (CORS), some captcha images hosted on different domains might not load directly. Ensure the image URL you provide allows cross-origin requests or host the captcha image on the same domain as your `index.html` for local testing.*

2.  **Solve the Captcha:**
    Once the page loads with the captcha image, an input field will appear. Type your solution into this field.

3.  **Submit and View Results:**
    Click the "Submit" button. The application will then display the text you entered and the time it took (in seconds) from the moment the image appeared until you submitted your solution.

## Code Explanation
The application is a single-page static web application built with HTML, CSS, and JavaScript.

*   **`index.html`**:
    *   This is the main entry point of the application.
    *   It contains an `<img>` tag to display the captcha, an `<input type="text">` field for the solution, and a `<button>` to submit.
    *   A `<div>` element is used to display the results (solved text and time taken).
*   **CSS (`<style>` block within `index.html`)**:
    *   Provides basic styling for a clean, user-friendly interface. It centers the content and ensures readability.
*   **JavaScript (`<script>` block within `index.html`)**:
    *   **URL Parameter Handling**: On page load, it reads the `url` query parameter from `window.location.search`. If a URL is found, it dynamically sets the `src` attribute of the `<img>` tag, making the captcha visible.
    *   **Timer Functionality**: A timer starts when the captcha image is successfully loaded and displayed.
    *   **Submission Logic**: An event listener is attached to the submit button. When clicked:
        *   It captures the text entered by the user.
        *   It calculates the elapsed time since the captcha image was displayed.
        *   The entered text and the calculated time (formatted to seconds) are then displayed in the results area.

## License
This project is licensed under the MIT License.

```
MIT License

Copyright (c) [Year] [Your Name or Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```