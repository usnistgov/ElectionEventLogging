# EventLoggingV1

- Table of Contents
  - Enumerations
    - *The **[DeviceType](#_18_2_43401a7_1448918170138_736592_4366)** Enumeration*
    - *The **[EventDispositionType](#_17_0_2_4_f71035d_1448386251626_459706_2440)** Enumeration*
    - *The **[HashType](#_19_0_43701b0_1551277104966_589263_4727)** Enumeration*
  - Classes
    - *The **[Device](#_18_2_43401a7_1458836797652_566165_4461)** Class*
    - *The **[ElectionEventLog](#_16_9_c0802fe_1373998775830_299520_2116)** Class*
    - *The **[ElectionEventLogDocumentation](#_19_0_43701b0_1551892560159_591563_4768)** Class*
    - *The **[Event](#_16_9_c0802fe_1373996817517_272063_1501)** Class*
    - *The **[EventIdDescription](#_19_0_43701b0_1551892560160_504752_4769)** Class*
    - *The **[EventTypeDescription](#_19_0_43701b0_1551892560160_283613_4770)** Class*

## Enumerations

### <a name="_18_2_43401a7_1448918170138_736592_4366"></a>*The **DeviceType** Enumeration*

![Image of DeviceType](Election_Event_Logging_UML_documentation_files/_18_2_43401a7_1448918170143_277540_4367.png)

Used in [Device](#_18_2_43401a7_1458836797652_566165_4461)::[Type](#_18_2_43401a7_1458837190975_379280_4518) to describe the type or usage of the device generating the event.

Name | Value
---- | -----
`adjudication`|Electronic adjudication function for reviewing absentee/mail-in ballots anomalies (blanks/overvotes/write-ins/unreadable ballots).
`ballot-activation`|Devices for enabling a vote capture device (VCD) to display a ballot, possibly directly connected to the VCD or through a smart card interface.
`bmd`|Ballot marking devices (voter facing).
`ballot-printing`|Marked ballot printing devices (voter facing).
`blank-ballot-printing`|On-demand blank ballot printers.
`dre`|Electronic voter stations, standalone or daisy chained to a DRE-controller (voter facing).
`dre-controller`|Network controller for electronic voting (poll worker facing).
`electronic-cast`|DREs, or other devices that store cast vote records electronically (voter facing).
`electronic-cast-paper`|DREs, or devices that store cast vote records electronically and also print a paper record (voter facing).
`electronic-poll-book`|Electronic poll book devices.
`ems`|Election management systems, including for pre- and post-election administration and reporting functions.
`scan-batch`|Scanning devices for batches of ballots, auto-feeding, e.g., Central Count (poll worker facing).
`scan-single`|Scanning devices for single-sheets, e.g., Precinct Count (voter facing), but could be used for Central Count by an election official.
`transmission-sending`|Remote transmission clients, e.g., for sending of unofficial results from a remote location to a central location (sending station).
`transmission-receiving`|Remote transmission hosts, e.g., for the receiving of unofficial results at a central location from a remote location (receiving station).
`other`|Used when no other value in this enumeration applies.

### <a name="_17_0_2_4_f71035d_1448386251626_459706_2440"></a>*The **EventDispositionType** Enumeration*

![Image of EventDispositionType](Election_Event_Logging_UML_documentation_files/_17_0_2_4_f71035d_1448386251632_323368_2441.png)

Used in [Event](#_16_9_c0802fe_1373996817517_272063_1501)::[Disposition](#_16_9_f2e0365_1375898006411_547543_2341) for types of event dispositions.

Name | Value
---- | -----
`failure`|For a failure disposition.
`na`|Used when the disposition is not applicable or there is no disposition.
`success`|For a successful disposition.
`other`|Used when no other value in this enumeration applies.

### <a name="_19_0_43701b0_1551277104966_589263_4727"></a>*The **HashType** Enumeration*

![Image of HashType](Election_Event_Logging_UML_documentation_files/_19_0_43701b0_1551277104994_705427_4749.png)

Used in [Hash](#_18_0_2_6340208_1485894593826_736413_4615)::[Type](#_18_0_2_6340208_1485894641846_811323_4646) to indicate the type of hash being used for an image file.

Name | Value
---- | -----
`md6`|To indicate that the MD6 message digest algorithm is being used.
`sha-256`|To indicate that the SHA 256-bit signature is being used.
`sha-512`|To indicate that the SHA 512-bit (32-byte) signature is being used.
`other`|Used when no other value in this enumeration applies.

## Classes

### <a name="_18_2_43401a7_1458836797652_566165_4461"></a>*The **Device** Class*

![Image of Device](Election_Event_Logging_UML_documentation_files/_18_2_43401a7_1458836797656_544780_4462.png)

Device contains information about the device generating election event logs. [Id](#_16_9_f2e0365_1375898077639_261665_2348) is the only required attribute, all other attributes are optional. If the device type is not found in the [DeviceType](#_18_2_43401a7_1448918170138_736592_4366) enumeration, Type is ‘other’ and [OtherType](#_18_2_43401a7_1448918045388_252688_4353) contains the appropriate type.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_18_2_43401a7_1458837370694_369735_4580"></a>`Details`|0..1|`String`|Used to associate any details with the event log.
<a name="_18_2_43401a7_1458837284745_638566_4548"></a>`{Event}`|0..*|`Event`|Used to describe a logged event.
<a name="_19_0_43701b0_1551362077643_666577_6063"></a>`HashType`|0..1|`HashType`|The type of the hash, from the [HashType](#_19_0_43701b0_1551277104966_589263_4727) enumeration.
<a name="_19_0_43701b0_1551362095000_687582_6067"></a>`OtherHashType`|0..1|`String`|If [HashType](#_19_0_43701b0_1551362077643_666577_6063) is 'other', the type of the hash.
<a name="_16_9_f2e0365_1375898077639_261665_2348"></a>`Id`|1|`String`|A serial number or otherwise identifier associated with the device.
<a name="_18_2_43401a7_1448918078516_548548_4357"></a>`Manufacturer`|0..1|`String`|Manufacturer of the device.
<a name="_18_2_43401a7_1458823425264_550724_4458"></a>`Model`|0..1|`String`|Model of the device.
<a name="_18_2_43401a7_1458837190975_379280_4518"></a>`Type`|0..1|`DeviceType`|Enumerated usage of the device, e.g., ems, scan-single, etc.
<a name="_18_2_43401a7_1448918045388_252688_4353"></a>`OtherType`|0..1|`String`|Used when [Type](#_18_2_43401a7_1458837190975_379280_4518) is ‘other’.
<a name="_18_2_43401a7_1458039926172_621476_4470"></a>`Version`|0..1|`String`|Version identification of the device.


### <a name="_16_9_c0802fe_1373998775830_299520_2116"></a>*The **ElectionEventLog** Class*

![Image of ElectionEventLog](Election_Event_Logging_UML_documentation_files/_16_9_c0802fe_1373998774598_571664_2115.png)

ElectionEventLog is the root class. It includes [Device](#_18_2_43401a7_1458836797652_566165_4461) for identifying the device(s) generating the election events, the date and time when the election event log was created, and an identification of the election. [Details](#_18_2_43401a7_1458825227267_28946_4470) is used as needed for additional description/details. [HashType](#_19_0_43701b0_1551362077643_666577_6063) is used to specify a cryptographic hash associated with the events, that is, an event log entry, using values from the [HashType](#_19_0_43701b0_1551277104966_589263_4727) enumeration. If the type of hash is not found in the [HashType](#_19_0_43701b0_1551277104966_589263_4727) enumeration, [HashType](#_19_0_43701b0_1551277104966_589263_4727) is ‘other’ and [OtherHashType](#_19_0_43701b0_1551362095000_687582_6067) contains the type of hash.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_18_2_43401a7_1458825227267_28946_4470"></a>`Details`|0..1|`String`|Used to associate any details with the event log.
<a name="_18_2_43401a7_1458837270842_751357_4527"></a>`{Device}`|0..*|`Device`|Used to describe the device(s) generating the election events.
<a name="_18_2_43401a7_1458039849744_695134_4466"></a>`ElectionId`|0..1|`String`|Identifies the election associated with the log.
<a name="_17_0_2_4_c0802fe_1377194442331_435875_2187"></a>`GeneratedTime`|1|`dateTime`|Identifies the date and time the log was generated.


### <a name="_19_0_43701b0_1551892560159_591563_4768"></a>*The **ElectionEventLogDocumentation** Class*

![Image of ElectionEventLogDocumentation](Election_Event_Logging_UML_documentation_files/_19_0_43701b0_1551892560301_503123_4850.png)

ElectionEventLogDocumention is the root class. It includes [EventIdDescription](#_19_0_43701b0_1551892560160_504752_4769) and [EventTypeDescription](#_19_0_43701b0_1551892560160_283613_4770), as well as other information for identifying the specific device associated with the election event documentation.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_19_0_43701b0_1551892560169_110651_4776"></a>`DeviceId`|0..1|`String`|A serial number or otherwise identifier associated with the device.
<a name="_19_0_43701b0_1551892560169_970324_4777"></a>`DeviceManufacturer`|1|`String`|Manufacturer of the device.
<a name="_19_0_43701b0_1551892560170_517440_4778"></a>`DeviceModel`|1|`String`|Model of the device.
<a name="_19_0_43701b0_1551892560170_28666_4779"></a>`DeviceVersion`|0..1|`String`|Version identification of the device.
<a name="_19_0_43701b0_1551892560168_64794_4775"></a>`{EventIdDescription}`|1..*|`EventIdDescription`|For associating a description with an event ID.
<a name="_19_0_43701b0_1551892560170_221772_4781"></a>`{EventTypeDescription}`|1..*|`EventTypeDescription`|For associating a description with an event type.
<a name="_19_0_43701b0_1551892560170_754063_4780"></a>`GeneratedDate`|1|`date`|Identifies the date the documentation report was generated.


### <a name="_16_9_c0802fe_1373996817517_272063_1501"></a>*The **Event** Class*

![Image of Event](Election_Event_Logging_UML_documentation_files/_16_9_c0802fe_1373996816799_682999_1500.png)

Event holds information about a specific event. [Severity](#_16_9_f2e0365_1375897866132_94017_2339) is an optional attribute for describing a severity indication for the event. If the event disposition is not found in the [EventDispositionType](#_17_0_2_4_f71035d_1448386251626_459706_2440) enumeration, [Disposition](#_16_9_f2e0365_1375898006411_547543_2341) is ‘other’ and [OtherDisposition](#_17_0_2_4_f71035d_1448386350889_251652_2466) contains the other disposition.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_17_0_2_4_c0802fe_1377195635357_173228_2381"></a>`Description`|0..1|`String`|Used for a brief description of the event.
<a name="_17_0_2_4_c0802fe_1377195646087_305689_2383"></a>`Details`|0..1|`String`|Used for additional information about the event, e.g., vendor reserved information.
<a name="_16_9_f2e0365_1375898006411_547543_2341"></a>`Disposition`|1|`EventDispositionType`|The disposition, e.g., success or failure, of the event.
<a name="_17_0_2_4_f71035d_1448386350889_251652_2466"></a>`OtherDisposition`|0..1|`String`|Used when [Disposition](#_16_9_f2e0365_1375898006411_547543_2341) is ‘other’.
<a name="_18_0_5_43401a7_1488989461419_677388_4253"></a>`Hash`|0..1|`String`|Contains a cryptographic hash of the event, encoded as a string.
<a name="_17_0_2_4_c0802fe_1377195615848_618029_2379"></a>`Id`|1|`String`|An identifier associated with the event.
<a name="_18_0_5_43401a7_1488989494413_340078_4257"></a>`Sequence`|1|`String`|A sequence number/string to uniquely identify the event in the log file.
<a name="_16_9_f2e0365_1375897866132_94017_2339"></a>`Severity`|0..1|`String`|Used for an indication of the severity of the event, as determined by the device vendor.
<a name="_16_9_f2e0365_1375897130018_465094_2311"></a>`TimeStamp`|1|`dateTime`|Identifies the date and time the event was generated.
<a name="_16_9_f2e0365_1375897810995_956635_2337"></a>`Type`|1|`String`|Used for the type of event, as determined by the device vendor.
<a name="_16_9_f2e0365_1375898485153_758275_2377"></a>`UserId`|0..1|`String`|An identifier associated with a user, as relevant.


### <a name="_19_0_43701b0_1551892560160_504752_4769"></a>*The **EventIdDescription** Class*

![Image of EventIdDescription](Election_Event_Logging_UML_documentation_files/_19_0_43701b0_1551892560293_491316_4849.png)

For associating a brief description with an election event ID, used in [ElectionEventLogDocumentation](#_19_0_43701b0_1551892560159_591563_4768)::[EventIdDescription](#_19_0_43701b0_1551892560168_64794_4775).

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_19_0_43701b0_1551892560171_404873_4784"></a>`Description`|1|`String`|Used for a brief description of the event.
<a name="_19_0_43701b0_1551892560171_302106_4785"></a>`Id`|1|`String`|An identifier associated with the event.


### <a name="_19_0_43701b0_1551892560160_283613_4770"></a>*The **EventTypeDescription** Class*

![Image of EventTypeDescription](Election_Event_Logging_UML_documentation_files/_19_0_43701b0_1551892560301_247583_4852.png)

For associating a description with an election event log type, used in [ElectionEventLogDocumentation](#_19_0_43701b0_1551892560159_591563_4768)::EventTypeDescription.

Attribute | Multiplicity | Type | Attribute Description
--------- | ------------ | ---- | ---------------------
<a name="_19_0_43701b0_1551892560172_590050_4787"></a>`Description`|1|`String`|Used for a description of the event type.
<a name="_19_0_43701b0_1551892560172_2117_4788"></a>`Type`|1|`String`|An identifier associated with the event type.


