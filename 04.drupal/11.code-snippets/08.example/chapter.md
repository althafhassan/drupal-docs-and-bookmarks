---
title: 'Example Class and Method'
---

class Popups
{
  private $entityQuery;
  private $entityTypeManager;

  public function __construct(QueryFactory $entityQuery, EntityTypeManagerInterface $entity_type_manager) {
    $this->entityQuery = $entityQuery;
    $this->entityTypeManager = $entity_type_manager;
  }



public function read($cid)
  {
    $nodes = $this->entityTypeManager->getStorage('node')->loadByProperties(['type' => 'book', 'cid' => $cid ]);

    return $nodes;
  }

}