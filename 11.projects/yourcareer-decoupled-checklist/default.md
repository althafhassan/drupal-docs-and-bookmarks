# ![](https://www.yourcareer.gov.au/themes/custom/yourcareer/images/your-career-logo.svg) Yourcareer Decoupled



# Security

* API Authentication

```
Available Options in Drupal.
https://www.drupal.org/project/rest_api_authentication
``` 

* Review CORS settings

```
Seckit is highly recommended module 
https://www.drupal.org/project/seckit 
``` 

* API root URL update/Allow only API read/Disable API not required to expose/Disable not required fields and review API doc
``` 
See Security Recommendation
``` 

* Review all routes to make sure access information are correct.
```https://www.drupal.org/project/routes_list

Module provides a simple dashboard with a list of all available routes in the system and access information.
It's useful for quick overview of permissions configuration and security check to ensure no hidden URLs are active with full access to anyone.
```  

* Use security review module to check any other findings. 
```
https://www.droptica.com/blog/security-review-module-drupal/
```
* Code Vulnerability scan
```
Open source vulnerability check - Use Synk/ other tools in GitLab.
Code Scan - Sonarqube  (Identifies Vulnerability and tech debt)
```

# Caching
```
 1. Both cache and cache purge should work for entities and APIs. 
 2. Check for any issues in Drupal/Json API/Akamai - https://techdocs.akamai.com/api-definitions/docs/api-gateway-ov
 3. API throttle and Request handling can be set up in Akamai. Will need to check this.
```

# Developer Documentation
```
Available through openAPI doc module. 
```