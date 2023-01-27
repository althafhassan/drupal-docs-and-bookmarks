---
title: 'Call method in controller from module'
---

* Add the class to examplemodule.services.yml 

* Inject the core services there.

services:
  examplemodule.cricket:
    class: Drupal\mymodule\Cricket
    arguments: ['@entity.query', '@entity_type.manager']
    
    Reference:
    https://drupal.stackexchange.com/questions/284981/how-to-call-method-of-controller-in-module-file-with-dependency-injection