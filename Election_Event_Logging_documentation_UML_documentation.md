# EventLoggingDocumentationV1-8

- Table of Contents
  - Enumerations
  - Classes
    - *The **[ElectionEventLogDocumentation](#_16_9_c0802fe_1373998775830_299520_2116)** Class*
    - *The **[EventIdDescription](#_16_9_c0802fe_1373996817517_272063_1501)** Class*
    - *The **[EventTypeDescription](#_18_2_43401a7_1459795591545_309185_4461)** Class*

## Enumerations

## Classes

### <a name="_16_9_c0802fe_1373998775830_299520_2116"></a>*The **ElectionEventLogDocumentation** Class*

![Image of ElectionEventLogDocumentation](Election_Event_Logging_documentation_UML_documentation_files/_16_9_c0802fe_1373998774598_571664_2115.png)

ElectionEventLogDocumention is the root class. It includes [EventIdDescription](#_16_9_c0802fe_1373996817517_272063_1501) and [EventTypeDescription](#_18_2_43401a7_1459795591545_309185_4461), as well as other information for identifying the specific device associated with the election event documentation.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_16_9_f2e0365_1375898077639_261665_2348"></a>`DeviceId`|0..1|`String`|A serial number or otherwise identifier associated with the device.
<a name="_18_2_43401a7_1448918078516_548548_4357"></a>`DeviceManufacturer`|1|`String`|Manufacturer of the device.
<a name="_18_2_43401a7_1449599140217_283811_4458"></a>`DeviceModel`|1|`String`|Model of the device.
<a name="_18_2_43401a7_1458242870949_712588_4466"></a>`DeviceVersion`|0..1|`String`|Version identification of the device.
<a name="_16_9_c0802fe_1374064398579_889747_1879"></a>`EventIdDescription`|1..*|`EventIdDescription`|For associating a description with an event ID.
<a name="_18_2_43401a7_1459795685676_276063_4496"></a>`EventTypeDescription`|1..*|`EventTypeDescription`|For associating a description with an event type.
<a name="_17_0_2_4_c0802fe_1377194442331_435875_2187"></a>`GeneratedDate`|1|`date`|Identifies the date the documentation report was generated.


### <a name="_16_9_c0802fe_1373996817517_272063_1501"></a>*The **EventIdDescription** Class*

![Image of EventIdDescription](Election_Event_Logging_documentation_UML_documentation_files/_16_9_c0802fe_1373996816799_682999_1500.png)

For associating a brief description with an election event ID, used in [ElectionEventLogDocumentation](#_16_9_c0802fe_1373998775830_299520_2116)::[EventIdDescription](#_16_9_c0802fe_1374064398579_889747_1879).

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_17_0_2_4_c0802fe_1377195635357_173228_2381"></a>`Description`|1|`String`|Used for a brief description of the event.
<a name="_17_0_2_4_c0802fe_1377195615848_618029_2379"></a>`Id`|1|`String`|An identifier associated with the event.


### <a name="_18_2_43401a7_1459795591545_309185_4461"></a>*The **EventTypeDescription** Class*

![Image of EventTypeDescription](Election_Event_Logging_documentation_UML_documentation_files/_18_2_43401a7_1459795591571_359384_4462.png)

For associating a description with an election event log type, used in [ElectionEventLogDocumentation](#_16_9_c0802fe_1373998775830_299520_2116)::EventTypeDescription.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_18_2_43401a7_1459795629548_422576_4483"></a>`Description`|1|`String`|Used for a description of the event type.
<a name="_18_2_43401a7_1459795656001_794403_4487"></a>`Type`|1|`String`|An identifier associated with the event type.


