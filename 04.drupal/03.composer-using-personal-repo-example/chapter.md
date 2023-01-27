---
title: 'Composer using personal repo example'
---

{ 
  "require": 
      { "vendor/my-private-repo": "dev-master" }, 
  "repositories": 
      [{ "type": "vcs", "url": "git@bitbucket.org:vendor/my-private-repo.git" } ] 
}