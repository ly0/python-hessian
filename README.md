About
-----

This is a python-hessian fork for python3.4

**python-hessian** is a Python implemention of Hessian, a binary web services
protocol. It supports the `Hessian 1.0.2 specification
<http://hessian.caucho.com/doc/hessian-1.0-spec.xtp>`_ and the
`Hessian 2.0 Serialization Protocol
<http://hessian.caucho.com/doc/hessian-serialization.html>`_. The library
is a fork of `mustaine <https://github.com/bgilmore/mustaine>`_, which is no
longer maintained. It provides a standard HTTP-based client
as well as a general-purpose serialization library.

Usage
-----

#### Using `pyhessian.client`

Testing against `Caucho’s <http://hessian.caucho.com/>`_ reference service:

```python
from pyhessian.client import HessianProxy
service = HessianProxy("http://hessian.caucho.com/test/test")
print service.replyDate_1()
```

#### Examples
Here is the example codes in situation which you need to serialize a java object to hessian.
```python
from pyhessian.protocol import cls_factory
from pyhessian.client import HessianProxy

NiceObject = cls_factory(
    name='com.company.objects.NiceObject',
    fields=['id', 'name', 'address']
    )

nice_object = NiceObject(id=998, name='Wondernaire', address='GFW Inside')

url = r'http://SOMEURL'
service = HessianProxy(url)
data = nice_object
res = service.NiceObjectSubmit(data)
```

Source
------

Up-to-date sources and documentation can always be found at the `python-hessian
GitHub site <https://github.com/theatlantic/python-hessian>`_.
