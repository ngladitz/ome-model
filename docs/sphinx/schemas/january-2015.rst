Changes for January 2015
========================


The list of the key changes for the January 2015 major release of the
OME-XML data model. This schema release will tie in with the Bio-Formats
5.1 release.

The new major release of the schema has a new namespace and all version
numbers are reset to 1. As a major release, any file that validated
correctly using the last major release will probably not validate
correctly using this new release. Some files that failed to validate
before will now be valid. It is important to update any file readers and
writers to understand the changes.

The version number of all schema files is now 1, except ome.xsd which
version number is 2.

This schema uses the new namespace:

::

    http://www.openmicroscopy.org/Schemas/[NameSpaceTitle]/2015-01/

For the OME schema

::

    http://www.openmicroscopy.org/Schemas/OME/2015-01/

and the schema file is located at

::

    http://www.openmicroscopy.org/Schemas/OME/2015-01/ome.xsd

Overview of changes
-------------------

- This version introduces a major new system of specifying units
  for the values stored as lengths, times, pressures, angles, temperatures,
  electric potentials (voltages), powers and frequencies.
  For more information see 
  :doc:`the OME system of units </developers/ome-units>`.
- Many annotation points have been added and some removed.
  Objects in the model are now directly annotatable or have a 1 to 1
  relationship with an object that is.


BinaryFile
^^^^^^^^^^

- There are no significant changes to this component.

OME
^^^

- Expanded documentation for ``AcquisitionDate`` describing supported
  precision.
- Updated documentation for ``NDFilter`` to reflect usage
- Added Annotation points (``AnnotationRef``) to:
    | ``Instrument``
    | ``Objective``
    | ``Detector``
    | ``Filter``
    | ``Dichroic``
    | ``LightPath``
    | ``LightSource``
- Added attributes to store:
    | ``Pixels: PhysicalSizeXUnit``
    | ``Pixels: PhysicalSizeYUnit``
    | ``Pixels: PhysicalSizeZUnit``
    | ``Pixels: TimeIncrementUnit``
    | ``Plane: DeltaTUnit``
    | ``Plane: ExposureTimeUnit``
    | ``Plane: PositionXUnit``
    | ``Plane: PositionYUnit``
    | ``Plane: PositionZUnit``
    | ``Channel: PinholeSizeUnit``
    | ``Channel: ExcitationWavelengthUnit``
    | ``Channel: EmissionWavelengthUnit``
    | ``StageLabel: XUnit``
    | ``StageLabel: YUnit``
    | ``StageLabel: YUnit``
    | ``ImagingEnvironment: TemperatureUnit``
    | ``ImagingEnvironment: AirPressureUnit``
    | ``Objective: WorkingDistanceUnit``
    | ``Detector: VoltageUnit``
    | ``Filter: CutInUnit``
    | ``Filter: CutOutUnit``
    | ``Filter: CutInToleranceUnit``
    | ``Filter: CutOutToleranceUnit``
    | ``LightSource: PowerUnit``
    | ``Laser: WavelengthUnit``
    | ``Laser: RepetitionRateUnit``
    | ``LightSourceSettings: WavelengthUnit``
    | ``DetectorSettings: VoltageUnit``
    | ``DetectorSettings: ReadOutRateUnit``
- Removed Annotation points from:
    | ``Pixels: AnnotationRef``
- Changed from int to float:
    | ``Channel: ExcitationWavelength``
    | ``Channel: EmissionWavelength``
    | ``Filter: CutIn``
    | ``Filter: CutOut``
    | ``Filter: CutInTolerance``
    | ``Filter: CutOutTolerance``
    | ``Laser: Wavelength``
    | ``LightSourceSettings: Wavelength``
- Added a general ``Map`` to ``ImagingEnvironment`` to store key-value pairs
- Added a new core type ``NonNegativeFloat``
- Added a new core element ``Map`` and associated complex type ``MapPairs``.
  This in turn contains a collection of ``M`` elements that store a mapped
  value, each with its associated ``K`` key attribute.
- Defined new enumerations with the permitted values for:
    | ``UnitsLength``
    | ``UnitsTime``
    | ``UnitsPressure``
    | ``UnitsAngle``
    | ``UnitsTemperature``
    | ``UnitsElectricPotential``
    | ``UnitsPower``
    | ``UnitsFrequency``
- Added a new ``GenericExcitationSource`` to light source types. This uses a
  ``Map`` of key-value pairs to store metadata for a light source that cannot
  be expressed as one of the other types.

OMERO
^^^^^

:file:`OMERO.xsd` is not included in this release.

ROI
^^^

- Added Annotation points to:
    ``Shape: AnnotationRef``
- Added attributes to store:
    ``ROI: StrokeWidthUnit``
    ``ROI: FontSizeUnit``

SA
^^

- Added a new ``MapAnnotation`` type. This makes use of the new
  ``Map`` element from ``ome.xsd`` to store a collection of key-value pairs.

SPW
^^^

- Added attributes to store:
    ``WellOriginXUnit``
    ``WellOriginYUnit``
    ``PositionXUnit``
    ``PositionYUnit``
- Removed Annotation points from:
    ``WellSample: AnnotationRef``

Upgrading and Downgrading
-------------------------

The XSLT transforms between June 2013 and January 2015 versions are
available here:

`http://www.openmicroscopy.org/Schemas/Transforms/2013-06-to-2015-01.xsl <http://www.openmicroscopy.org/Schemas/Transforms/2013-06-to-2015-01.xsl>`_

`http://www.openmicroscopy.org/Schemas/Transforms/2015-01-to-2013-06.xsl <http://www.openmicroscopy.org/Schemas/Transforms/2015-01-to-2013-06.xsl>`_

