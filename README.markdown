# gsutil
#### Clone plus enhancements to the Google Storage command-line tool at http://code.google.com/p/gsutil/
****

I have added a push command to upload local directories to a cloud uri only if the files have changed.

## Push Command
#### Syntax
        gsutil push [-o] [-p] [-y] src_uri dst_uri
#### Options
        -o : overwrite. Upload files always regardless if objects differ.
        -p : prune. Delete objects at cloud_uri that do not exist locally.

#### Sample Usage
        $./gsutil push -opy /home/kwo/gsutil gs://code.repo/gsutil

## Roadmap
 - add confirmation prompt and listing of what actions will be performed
 - cache md5 calculation of local files between runs
