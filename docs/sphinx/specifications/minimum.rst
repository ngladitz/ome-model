Minimum specification
=====================


This was developed in conjunction with the September 2009 release of the
OME-XML Model and has been updated to the June 2016 release.

A minimum specification OME file has been defined. This is best viewed
as being the minimum required for the display of an image. A sample of
the structure is:

.. literalinclude:: minimum-specification.ome.xml

Alternative valid forms:

-  would have a ``<TiffData/>`` block instead of the ``BinData``
   block (this would be used in the header of an OME-TIFF file)
-  would have a ``<MetadataOnly/>`` block instead of the ``BinData``
   block (this would be used as a companion to one or more ``BinaryOnly``
   OME-TIFF files)

.. note:: A units system was added in January 2015. This sample assumes the
   default unit for each value is used.
