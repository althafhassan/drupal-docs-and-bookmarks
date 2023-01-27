---
title: Entityqueue
---

**Create Entityqueue**

**URL**

/admin/structure/entityqueue

**Options**

Ability to add single and multiple subqueues. 

Auto update entityqueue. May require some tweaking based on requirements.

Additional form items can be added to entityqueue configuration using custom code that can attach to the existing form.

Currently using single entityqueue. Multiple subqueues is also working and can be used in future. Basically multiple subqueue contains 2 single subqueues. 
One use case for Multiple subqueues  is when some items on the top of queue doesn't change frequently and other items are updated regularly. This makes extra work to make sure first item is not changed.

**Adding Items Entityqueue**

Entityqueue can be used with other entities. 

With items you need the entity created before adding it.

**How is it added in the current CMS**

Simple content type just to add featured contents and also to add featured content that can map external URL.

With content types that is used to build pages.

An option to add to queue is provided in the content edit form. Default is not selected.

**For Developer**

* An option to add to queue is provided in the content edit form

The field for above is added as a reference to field content using views (type: entity reference). This way there is ability to filter entity subqueues.

While creating the field choose 

**Type of Item to reference: Entity Subqueue**

Allowed number of items set to unlimited so a content can be added to different subqueues.

And in Edit form under Reference Type, 

Choose Entity Reference method - Default

Then Select the subqueues to appear in the content page add/edit form.

hook_entity_insert is used to add the content item to queue. Since hook_entity_insert happens after node content is created, it enables to add item to subqueue using the entity title.

Also this enables option for content to be pushed to different queues. Just few lines of code.

use Drupal\Core\Entity\EntityStorageException;
use Drupal\Core\Entity\EntityInterface;
use Drupal\entityqueue\Entity\EntitySubqueue;

/**
 * Implements hook_entity_insert().
 *
 * @throws EntityStorageException
 */
function yourcareer_entityqueue_entity_insert(EntityInterface $entity) {
  $type = $entity->getEntityTypeId();
  if($type == 'node' && $entity->hasField('field_yc_feature_grid')) {
    if (isset($entity->get('field_yc_feature_grid')->target_id)) {
      $subqueue = EntitySubqueue::load($feature_grid_id);
      // Adds the given entity to a subqueue.
      $subqueue?->addItem($entity)->save();
    }
  }
}

Numbers of items in a subqueue

Selecting entities for adding to subqueue

Add item to top or bottom of queue.

Entity Auto add is also possible. Will need to provide a checkbox to add to auto queueue. See below an example to Exclude entities from queue that are enabled for auto queueue. This is when you need contents to be added queue manually from selected content types and only some contents from some content type.

  // Add a textarea field for excluding entities from automatically adding to queue.
    $form['entity_settings']['settings']['handler_settings']['auto_entityqueue']['ignore_entities'] = array(
      '#default_value' => $entity_settings['handler_settings']['auto_entityqueue']['ignore_entities'],
      '#description' => t('Add entities to exclude using comma seperated for multiple.'),
      '#title' => t('Exclude entities from queue'),
      '#type' => 'textarea',
    );
    
  Use this check in the entity hook and add items according to use case scenario.
  
  Storage entities can also be used to create bundles which can be added to entity subqueue.
