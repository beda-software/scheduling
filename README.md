# Scheduling

This repository describes the requirement for a scheduling module that may use as a test task for new developers and/or for testing new technologies and develop approaches.

## User roles
There is only one user in the system. This user has super administrator permissions.

## Pages
* Login page
* [Patient](https://www.hl7.org/fhir/patient.html) list/Patieint details
* [Practitioner](https://www.hl7.org/fhir/practitioner.html) list/Practitioner detail
* [Location](https://www.hl7.org/fhir/location.html) list/Location detail
* [Schedule](https://www.hl7.org/fhir/schedule.html) and [Slot](https://www.hl7.org/fhir/slot.html) mangment for Practitioner.
* [Schedule](https://www.hl7.org/fhir/schedule.html) and [Slot](https://www.hl7.org/fhir/slot.html) mangment for Location.
* Book an appointment form.

## Flow
Patients, Practitioners, Locations are actors of the appointment.   
To book an appointment you need to select a patient, one or more practitioners and a location.  
Then the system should load slots for the practitioner(s) and the location and calculate the overlap slots. (Slots that fit all actors).  
The user will select a slot for the appointment and create a new appointment. The actor's slots should be marked as `busy` and be removed from further booking.

## Technology requirements
* FHIR server should be used as a backend API.
* All data manipulation should be implemented on the frontend. In the case of transactional requests [bundle transactions](http://hl7.org/fhir/http.html#transaction) shall be used. 




