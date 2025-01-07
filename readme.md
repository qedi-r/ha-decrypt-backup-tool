# Home Assistant Backup Decryption Tool

This tool helps you decrypt Home Assistant backups outside of Home Assistant, using your emergency kit.

## Prerequisites

- Python 3.7 or newer
- `cryptography` package installed (`pip install cryptography`)

## Setup

1. Download the script (`decrypt_backup.py`)
2. Make it executable:
   ```bash
   chmod +x decrypt_backup.py
   ```

## Usage

1. Create a new directory for decryption
2. Place these files in the directory:
   - The script (`decrypt_backup.py`)
   - Your backup .tar file
   - Your emergency kit text file (optional)
3. Run the script:
   ```bash
   ./decrypt_backup.py
   ```
   - If an emergency kit file is present, the script will automatically extract the key
   - If no kit file is found or the key can't be extracted, you'll be prompted to enter the key manually

The script will automatically:
- Find your emergency kit and extract the encryption key
- Process all backup files in the directory
- Create extracted directories with the decrypted content

## Troubleshooting

If you encounter any issues:

1. Make sure you have the `cryptography` package installed:
   ```bash
   pip install cryptography
   ```

2. Verify that your emergency kit file contains the encryption key
3. Ensure your backup files are in the correct format (.tar)
4. Check that all files are in the same directory as the script

## Note

This tool is designed to work with Home Assistant backups created with encryption enabled. It will not work with unencrypted backups or backups from other systems.

## Security

- Keep your emergency kit secure - it contains your encryption key
- After decryption, store the decrypted files in a secure location
- Consider deleting the emergency kit file after use if you don't need it

## Support

If you encounter issues, you can:
1. Verify your emergency kit is valid by checking it in Home Assistant
2. Ensure your backup files were properly downloaded
3. Try creating a new backup in Home Assistant to test with
