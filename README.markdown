# gsutil
#### Clone plus enhancements to the Google Storage command-line tool at http://code.google.com/p/gsutil/
****
I have added a push command to upload local directories to a cloud uri only if the files have changed.

## Push Command
Push directory to cloud uri, only uploading if the files differ.
### Syntax
		gsutil push [-p] [-s] [-y] src_uri dst_uri
### Options
		-p : prune.     Delete objects at cloud_uri that do not exist at src_uri.
		-s : simulate.  Simulate actions but do not actually perform them.
		-y : yes.       Bypass confirmation prompt, assuming yes.
### Arguments:
		src_uri         file uri that points to a directory
		dst_uri         cloud uri

### Notes
Note that object names of local files uploaded to the cloud uri are calculated by prepending the cloud_uri, which may include a prefix, to the name of the local file relative to the src_uri.  For example, suppose we have the directory `/var/log/nginx` with the following files in it:

		access.log
		access.log.1
		access.log.2.gz
		access.log.3.gz
		access.log.4.gz

If we push the directory to the cloud uri `gs://log.files/http/logs`

		gsutil push /var/log/nginx gs://log.files/http/logs

then we end up with the following in the bucket

		gs://log.files/http/logs/access.log
		gs://log.files/http/logs/access.log.1
		gs://log.files/http/logs/access.log.2.gz
		gs://log.files/http/logs/access.log.3.gz
		gs://log.files/http/logs/access.log.4.gz

## Roadmap
 - cache md5 calculation of local files between runs
