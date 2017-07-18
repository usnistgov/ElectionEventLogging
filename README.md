# Voting - Election Event Logging CDF Specification

This directory holds an election event logging common data format specification as well as related information and files that have been created by NIST and collaborators. The specification is expected to be required in the next VVSG under development by NIST and the Election Assistance Commission (EAC).  

The documentation is located on https://pages.nist.gov/ElectionEventLogging.

The election event logging specification is for election event logs produced by election devices used in U.S. states and territories.  The logs contain information generated by voting-related applications such as election management systems (EMS), electronic pollbooks, ballot marking devices, ballot scanners, or other vote-capture applications that are operating on the election devices.  The sorts of information logged includes information required in the U.S. Election Assistance Commission (EAC) Voluntary Voting System Guidelines (VVSG), however manufacturers may include additional information in the logs.
The purpose of this specification is to provide a concise, interoperable XML format for manufacturers to integrate into their voting equipment and for election offices, researchers, testing laboratories and other groups to use in their own software.  The advantages of using this specification include:
 - Election logs are in the same, defined format regardless of device manufacturer.
 - Manufacturers can use the same, defined format for defining event codes and other information that may be specific to their own equipment.
 - Analyzing election logs produced by different types of equipment and different manufacturers is made significantly easier.

There are two models and associated schemas, one for the log file and one for a documentation file that is to be produced by mnaufacturers for each device; the documentation file provides definitions for the event IDs and event types used in the log file.

Contact [John P. Wack](mailto:john.wack@nist.gov) for questions and more information.
