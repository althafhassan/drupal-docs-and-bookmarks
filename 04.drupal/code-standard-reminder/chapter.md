---
title: 'Code Standard'
---

**Parameter and return typehinting**

Beginning with Drupal 9, parameter and return typehints should be used wherever possible. Example function definition using parameter and return typehints:

public function myMethod(MyClass $myClass, string $id): array {
  // Method code here.
}

**Mixed datatypes**

mixed is only needed in rare cases where a more specific data type cannot be identified (for example, for the return values of callbacks, or markup strings that can be either markup objects or scalar strings). A need for mixed or a union type is often a sign that the code should possibly be refactored.

**Add context to string**
https://www.drupal.org/node/1369936