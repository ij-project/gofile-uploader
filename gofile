#!/bin/bash

# Check if a file argument is provided
if [[ "$#" == '0' ]]; then
    echo -e 'ERROR: No File Specified!' && exit 1
fi

# Store the file path, preserving spaces
# $1 is the first command-line argument
FILE="$1"

# Query GoFile API to find the best server for upload
# Use jq to parse JSON response and extract the server name
# Add a User-Agent (-A) because sometimes GoFile blocks default curl requests.
SERVER=$(curl -s -A "Mozilla/5.0" https://api.gofile.io/servers | jq -r '.data.servers[0].name')

# Check if jq actually returned a valid server
# If not, default to "store1" or exit.
if [[ "$SERVER" == "null" || -z "$SERVER" ]]; then
    echo "Warning: API did not return a valid server. Trying fallback (store1)..."
    SERVER="store1"
fi

echo "Uploading to ${SERVER}.gofile.io..."

# Upload the file
# Add User-Agent here as well to ensure the upload is accepted.
LINK=$(curl -# -A "Mozilla/5.0" -F "file=@$FILE" "https://${SERVER}.gofile.io/uploadFile" | jq -r '.data.downloadPage') 2>&1

# Verify and display the download link
# Quoting $LINK preserves any spaces or special characters in the URL

if [[ "$LINK" == "null" || -z "$LINK" ]]; then
    echo "Upload failed. Please check your internet or GoFile API status."
    exit 1
fi

echo "Done!"
echo "$LINK"

# Print a blank line for better readability
echo
