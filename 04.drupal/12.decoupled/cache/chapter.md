---
title: Cache
---

Module:
https://www.drupal.org/project/jsonapi_boost

Patches:
https://www.drupal.org/project/drupal/issues/3039730 is a simple issue which is making sure that if you are requesting information of related entities then it statically caches the resource type information for that relationship so that when multiple entities of the same entity type and bundle are requested it doesn’t have to collect the resource type information for the related entities over and over again.

https://www.drupal.org/project/drupal/issues/2819335 adds a cache layer to store the normalized entities so that if we need the normalized version of an entity we can just get it from the cache instead of normalizing the whole entity again which can be a very expensive process.

https://www.drupal.org/project/drupal/issues/3018287 introduces new cache backend to store JSON:API resource type information which was stored in the static cache. This means that instead of creating JSON:API resource types every request, we are just creating them once after cache clear.