Usage
===================================


Model Setup
-----------------------------

Import the field inside your models.py and assign it to an attribute just like
you would with a normal django file. ::

    
    from ccthumbs.fields import ImageWithThumbsField
    
    CCTHUMBS_SIZES = (
            (200,200),
            (640, 480),
            (1200, 960)
    )
    
    class SomeModel(models.Model):
        img = ImageWithThumbsField(
                    upload_to='somemodel/%Y/%m/%d',
                    sizes=CCTHUMBS_SIZES)


Accessing Images
---------------------------------------------------

You access the various image sizes from a method on the model field. In the
above example we defined three sizes :

* 200 x 200
* 640 x 480
* 1200 x 960

You would be able to access those images from an instance of ``SomeModel``
using the following::

    my_somemodel_instance.img.url_200x200()
    my_somemodel_instance.img.url_640x960()
    my_somemodel_instance.img.url_1200x960()


.. note :: If you're access the images in a template you should omit the parenthesis.
