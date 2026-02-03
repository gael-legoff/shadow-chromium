**Usage**

    shadow-chromium edit
    shadow-chromium run PROFILE [URL]

**Description**

This script creates shadow copies of the Chromium user data directory and run Chromium in them.  
This allows the use of throwaway user-configured profiles.  
Profiles and all their data are discarded when Chromium is closed.  
This script works best on BTRFS or XFS where it can take advantage of reflink copy (`cp --reflink=auto`).  
Reflinks allow no-cost copy-on-write (COW) operations where only modified data is written to disk.  

**Howto**

* First, create profiles: `shadow-chromium edit`.
* Create as many profiles as needed (Personal, Banking, Shopping, ...).
* Execute Chromium on a shadow profile: `shadow-chromium run Personal`.
* Chromium will start in your temporary profile.
* When Chromium is closed, the temporary profile is discarded.

**Commands**

    edit   Edit profiles
    run    Run Chromium in a temporary profile. Profile is mandatory, URL is optional

**Examples**

    shadow-chromium edit
    shadow-chromium run Personal
    shadow-chromium run Disposable https://www.example.com/

Note: The `run` command requires the profile as its first argument.
