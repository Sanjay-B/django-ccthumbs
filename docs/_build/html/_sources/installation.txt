Installation
=====================================

Install via pip::

   pip install django-ccthumbs


Import the field inside your models.py and assign it to an attribute just like
you would with a normal django file. ::

    
    from django.conf import settings
    from ccthumbs.fields import ImageWithThumbsField
    
    
    class SomeModel(models.Model):
        img = ImageWithThumbsField(
                    upload_to='somemodel/%Y/%m/%d',
                    sizes=settings.CCTHUMBS_SIZES)

where ``settings.CCTHUMBS_SIZES`` is a tuple of tuples, each of which contains a
width and a height ::

    CCTHUMBS_SIZES = (
            (200,200),
            (640, 480),
            (1200, 960)
    )


