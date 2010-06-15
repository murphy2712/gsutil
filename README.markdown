# gsutil
#### Clone plus enhancements to the Google Storage command-line tool at http://code.google.com/p/gsutil/
****
I have added a push command to copy objects from one URI to another only if they differ.

## Push Command
Copy objects from one URI to another only if they differ.
### Syntax
		gsutil push [-p] [-s] [-y] src_uri dst_uri
### Options
		-p : prune.     Delete objects at cloud_uri that do not exist at src_uri.
		-s : simulate.  Simulate actions but do not actually perform them.
		-y : yes.       Bypass confirmation prompt, assuming yes.

## Roadmap
 - add progress bar for individual files
 - cache md5 calculation of local files between runs
