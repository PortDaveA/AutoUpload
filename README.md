# Automated Video Upload System for Zoom Clips & YouTube

An automated Google Apps Script solution that monitors a Google Drive folder and automatically uploads new video content to both Zoom Clips and YouTube. Features email notifications and upload tracking.

## Features

- 🔄 Automatic monitoring of Google Drive folder for new MP4 files
- ⬆️ Simultaneous uploads to both Zoom Clips and YouTube
- 📧 Email notifications for upload status and script monitoring
- 🎯 Intelligent file tracking to prevent duplicate uploads
- ⏱️ Configurable checking intervals (default: 5 minutes)
- 📊 Detailed logging and status reporting

## Prerequisites

1. Google Workspace account
2. Zoom Developer Account with Server-to-Server OAuth app
3. YouTube Data API access with OAuth 2.0 credentials
4. Google Apps Script enabled

## Setup

1. Create a new Google Apps Script project
2. Copy the code into your script editor
3. Set up your configuration variables at the top of the script:
   ```javascript
   var NOTIFICATION_EMAIL = "your-email@domain.com";
   var FOLDER_ID = "your-google-drive-folder-id";
   ```

4. Configure your API credentials:
   ```javascript
   // Zoom credentials
   var CLIENT_ID = 'your-zoom-client-id';
   var CLIENT_SECRET = 'your-zoom-client-secret';
   var ACCOUNT_ID = 'your-zoom-account-id';

   // YouTube credentials
   var YOUTUBE_CLIENT_ID = 'your-youtube-client-id';
   var YOUTUBE_CLIENT_SECRET = 'your-youtube-client-secret';
   var YOUTUBE_REFRESH_TOKEN = 'your-youtube-refresh-token';
   ```

## Usage

1. Start the automatic monitoring:
   ```javascript
   function createTrigger() {
     // Run this function once to start automatic monitoring
   }
   ```

2. Check script status:
   ```javascript
   function checkTriggerStatus() {
     // Run this to verify script is running and get next check time
   }
   ```

3. Place MP4 files in your designated Google Drive folder

## How It Works

1. **Monitoring**: Script checks the specified folder every 5 minutes for new MP4 files
2. **Upload Process**:
   - Uploads new videos to Zoom Clips
   - Simultaneously uploads to YouTube (as private videos)
   - Tracks uploaded files to prevent duplicates
3. **Notifications**: Sends email updates for:
   - Script start/stop status
   - Successful uploads
   - Failed uploads with error details
   - Next scheduled check time

## File Management

- Only processes MP4 files
- Maintains a record of uploaded files using Google Apps Script's Properties Service
- Skips previously uploaded files automatically
- Supports large files through chunked uploading

## Notifications

Email notifications include:
- Upload summaries with success/failure status
- Clip IDs for successful uploads
- Error details for failed uploads
- Script status updates
- Next scheduled check time

## Error Handling

- Comprehensive error catching and reporting
- Automatic retry mechanism for failed uploads
- Detailed logging for troubleshooting
- Email notifications for critical errors

## Limitations

- Maximum file size subject to Google Drive and API limits
- YouTube uploads are set to private by default
- Script runs are limited by Google Apps Script quotas
- Only processes MP4 video files

## Security Notes

- Store API credentials securely
- Use appropriate file permissions in Google Drive
- Regularly monitor script execution logs
- Update API credentials periodically

## Troubleshooting

1. Check script execution logs in Apps Script editor
2. Verify trigger status using `checkTriggerStatus()`
3. Ensure all API credentials are valid
4. Check email notifications for error details

## Contributing

[Feel free to suggest useful extensions.]



---

⚠️ **Security Note**: Never commit this script with actual API credentials. Always use environment variables or Google Apps Script's Properties Service for sensitive information.
