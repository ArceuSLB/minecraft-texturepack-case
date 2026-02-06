# Static Analysis

## Environment
The analysis was performed using a Kali Linux virtual machine.  
The goal was to check if a suspicious Minecraft texture pack contained any malicious files.  
Only static analysis was conducted, no files were executed.

## Evidence
The following evidence was collected during the analysis:
- File hashes (MD5 and SHA256) stored in `Evidence/hashes.txt`
- Archive content listing stored in `Evidence/zip_list.txt`

## Analysis Process
1. The file type was checked to confirm that the archive was a ZIP file.
2. Cryptographic hashes were calculated to uniquely identify the file.
3. The contents of the ZIP archive were listed using `unzip -l` without extracting the files.
4. The archive listing was reviewed to look for common malicious indicators, such as:
   - Executable or script files (`.exe`, `.bat`, `.ps1`, `.js`)
   - Double file extensions
   - Unusual directories unrelated to Minecraft resource packs

## Findings
- The archive contains files and directories consistent with a legitimate Minecraft texture pack.
- Standard resource pack files such as `pack.mcmeta`, `pack.png`, and the `assets/` directory were present.
- No executable or script files were found in the archive.
- No signs of malicious content were identified during static analysis.

## Conclusion
Based on the results of the static analysis, the file was determined to be a false positive.  
Although the file itself is legitimate, the distribution method through social platforms like Discord can still pose a risk due to social engineering tactics.

