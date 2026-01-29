## Purpose
This application should be able to open a QTI Zip file, edit the contents, and save the zip file with the edits

## Objectives
### Requirements - Anonymous
1. Upload a ZIP file
	- File should be validated for correct formatting; Invalid formatting will be rejected holistically
	- file exists for as long as the session is valid; avoid loading into Memory, long-term; cache directory is best
	- uploaded file should be renamed 24-char sequence; refer to Wikipedia approach
		- The tail of the file name should be a DateTime format: CCYYMMDD_HHmmSS
	- All site processes dealing with the Uploaded File will use the 24-char sequence name
	- ZIP file and content must adhere to QTI 2.2 specification
2. Local Storage
	- Uploaded zip file will go into a cache-like directory
	- Provide a way for the user to "save" edits to a local directory
3. Provide a simple web interface that provides the editing functionality needed
	- Interface should allow for users to select questions from the zip file
	- Interface should allow for users to edit Questions and associated Answers
4. Status Feedback
	- On Upload a spinner should be visible in Modal mode
	- On Export a spinner should be visible in Modal mode

### Optionals - Authenticated
1. Authentication hierarchy and infrastructure
	- Registration page (no 3rd-party tools)
	- Account Information
	- No Memorization; session expires (30 mins +/-, no activity), account needs to login again
2. Authorization hierarchy and infrastructure
	- Role-based authorization
	- Role-based components
	- Roles: Anon, Auth-Free, Auth-Tier1, Auth-Tier2, Auth-Admin
3. Share-Drive (Dropbox, Google Drive, One-Drive, et al)
	- Will require a Registered Account
	- Will need to have an encrypted storage solution for SSO tickets
	- Does not have be the same account registered
	- Only active when user session is still valid
4. Export/Upload
	- The spinner text should show status of the process currently running


## References:
* QTI 2.2: https://www.1edtech.org/standards/qti/index#QTI22
* Modal Window: https://en.wikipedia.org/wiki/Modal_window
* 