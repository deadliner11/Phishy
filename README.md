# Phishy

Phishing URL detection tool adapted from my dissertation project which revolved around anti-phishing on Android devices (full paper can be found at: http://mydo.cx/M2RmYThi). 

Designed and tested on Debian based systems.

## Usage

*~$ ./phishy **'URL'***

**NOTE: ensure to _chmod +x_ the 'phishy' file before usage!**
<br/>
## Implemented Phishing Detection Techniques

### White/Blacklisting

- IP and URL blacklisting
- IP, URL and domain whitelisting
- Typoswatting detection in domains/subdomains

### URL Feature Extraction and Classification via ML
This part of the tool extracts 23 features from the user submitted URL and determines its legitimacy via a supervised Random Tree Model. Makes use of the *python-weka-wrapper* library.

#### Features

| | | | | | |
|:---:  |:---:  |:---:  |:---:  |:---:  |:---:  |
|Length of URL|Length of domain |Length of path|Depth of path|Number of percent symbols in the URL|Number of underscores in the URL
|Number of ampersands in the URL|Number of numbers in the URL|Number of hash symbols in the URL|Number of dashes in the URL|Number of dots in the URL|Whether a tilde is present in the URL
|Whether an ‘at’ symbol (@) is present in the URL|Number of subdomains|Number of dashes in the domain|Whether a Top-Level Domain (TLD) is contained within the subdomain(s)|Whether the domain is an IP address|Whether there is a double slash present in the path
|Number of URL queries|Scheme (HTTPS or HTTP)|Whether the URL’s combined top and second leveldomains appear in the first page of a Google Search|Whether the URL’s corresponding webpage has links within characteristic of a phishing page i.e. dead links orthose which go to a different domain||||
<br/>

**NOTE: Feature extraction and classification via ML is only used if the submitted URL isn't flagged up by the whie/blacklist test**
<br/>
## Requirements (INCOMPLETE)

- Python3
- Java



