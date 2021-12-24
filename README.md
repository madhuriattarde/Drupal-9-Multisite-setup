## Drupal 9 Multisite setup:

Here, Root site is http://www.drupal9.local/

Subsites or sites within root site are http://site1.drupal9.local/ and http://site2.drupal9.local/ 


**Lets start with some easy steps:**

1) To start the setup, first install Drupal 9 on a server with the database name 'drupal9'.    
   After installation create a virtual host for the root site as http://www.drupal9.local/

2) Create directory structure for multisites.                  
   Create folders for site1 and site2 as:      
    /drupal9/sites/site1.drupal9.local           
    /drupal9/sites/site2.drupal9.local

3) Create databases for site1 and site2 as 'drupal9_site1' and 'drupal9_site2.

4) Let the root site aware about multisites. Create an $sites array in sites.php

    Make a copy of /drupal9/sites/example.sites.php called /drupal9/sites/sites.php

5) Edit sites.php to add array. Add following array at the end of the file.
   ```
      $sites = array(
            	   'site1.drupal9.local' =>'site1.drupal9.local', 
            	   'site2.drupal9.local'=>'site2.drupal9.local' 
               ); 
   ```
   
6) Create virtual hosts for site1 and site2.
   
   site1 : http://site1.drupal9.local/
   site2 : http://site2.drupal9.local/ 
  
  Note: Here virtual hosts for multisites should point to root site, not to sites subdirectories.

7) Now make settings for site1 and site2.
   Copy /drupal9/sites/default/default.settings.php to the new site's directories as settings.php:
   /sites/site1.drupal9.com/settings.php
   /sites/site2.drupal9.com/settings.php

8) Now finish the installation for site1 and site2 by visiting the domains http://site1.drupal9.local/ and http://site2.drupal9.local/
 
 
 Directory Structure for Multisite:
```
--core
 
--sites
  --site1
    --modules
    --themes
  
  --site2
    --modules
    --themes    
```
