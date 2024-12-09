# KOLS.ASIA Photo Uploader

## Overview
This is a simple web application for uploading photos and form data to a Make.com webhook. Users can input details such as campaign code, social media handle, and platform information, then upload multiple photos. The data and photos are sent directly to the specified Make.com webhook endpoint.

## Features
- Upload multiple photos simultaneously.
- Collect user input fields like:
  - Campaign Code
  - Social Media Handle
  - Platform selection.
- Conditional dropdown for "Lemon8" platform to specify the type of photo.
- Remove all selected photos with a single button click.
- Sends all form data and photos to a Make.com webhook for processing.

## How It Works
1. **User Input:**
   - Fill out the campaign code and social media handle.
   - Select the platform from the dropdown menu. If "Lemon8" is selected, an additional dropdown will appear for specifying the type of photo (Reach or Engagement).
   - Select one or more image files to upload.

2. **Form Submission:**
   - When the "Upload Photos" button is clicked, the form data and photos are packaged into a `FormData` object.
   - The `FormData` object is sent via a POST request to the Make.com webhook.

3. **Webhook Endpoint:**
   - The webhook URL is: `ENTERYOURWEBHOOK`
   - The webhook processes the received data and handles further actions as defined in your Make.com scenario.

4. **Feedback:**
   - On successful upload, a success message is displayed.
   - If an error occurs, it is logged in the console and an alert notifies the user.

## Files
### HTML Structure
- Contains a form with fields for campaign code, social media handle, platform selection, and file input.
- Includes a success message element to display feedback to the user.

### CSS Styling
- Simple and clean UI design with responsive styling.
- Highlights buttons and active elements with hover effects.

### JavaScript Functionality
- Handles form submission and file uploads.
- Sends form data and files to the Make.com webhook via a `fetch` API POST request.
- Displays conditional dropdown for "Lemon8" platform selection.
- Provides error handling and success feedback.

## How to Use
1. Open the `index.html` file in any modern web browser.
2. Fill in the required fields:
   - Campaign Code
   - Social Media Handle
   - Platform
   - (Optional) Lemon8 type, if applicable.
3. Select photos to upload using the file input.
4. Click "Upload Photos."
5. Wait for the success message or address any errors shown in an alert.

## Requirements
- A modern web browser with JavaScript enabled.
- An active Make.com scenario configured to process the data sent to the webhook.

## Webhook Integration
The Make.com webhook URL (`ENTERYOURWEBHOOK`) is hardcoded in the script. It accepts:
- Form fields as `multipart/form-data`:
  - `campaignCode`
  - `socialMediaHandle`
  - `platform`
  - `lemon8Type` (if applicable).
- Photo files as additional parts of the same `FormData` object.

## Error Handling
- Alerts the user if no files are selected.
- Displays an error alert if the webhook POST request fails.
- Logs detailed error information in the browser console for debugging.

## Customization
1. **Webhook URL:**
   - Replace the webhook URL in the JavaScript with your Make.com webhook.

2. **Styling:**
   - Update the CSS in the `<style>` block to customize the appearance.

3. **Validation:**
   - Add more validation checks to the JavaScript if required (e.g., file type or size restrictions).

## Security Notes
- Do not use this code in production without validating and sanitizing inputs server-side.
- Make sure the Make.com webhook scenario is secure and configured to handle data appropriately.

## License
This code is provided "as-is" without warranty. Use it as a starting point for your implementation.

