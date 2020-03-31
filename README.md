Request and Response models
=====
Is a common interfaces for reducing coupling.

Imagine a minimal symfony controller:

*before:*
```php

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;

class SomeController extends AbstractController {
    public function indexAction(Request $request): Response
    {
        // ...
    }
}
```

*after:*

```php

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use YourApp\Model\RequestModel\SomeIndexRequestModel;
use YourApp\Model\ResponseModel\SomeIndexResponseModel;

class SomeController extends AbstractController {
    public function indexAction(SomeIndexRequestModel $validModel): SomeIndexResponseModel
    {
        // ...
    }
}
```

Did you see this? We reduced coupling for free!

That's why this library is.
