# Domain Modules

## Energy

Thermodynamics: Various forms of energy and their conversion.

Especially: Sun rays, wind and weather, coal, nuclear, solar, batteries, electronics (computers, smart phones, sensors, embedded devices), electric devices (motors, microwaves, oven, light, electric vehicle).

## Power

### Physics

Power production: Solar, wind, nuclear, coal, biogas, battery discharge, hydroplant unloading

Power consumption: Battery charge, hydroplant loading, immediate electric device (microwave, washing machine, phone/laptop charger, static computer, lights, oven, mixer).

Power transmission: voltage, transformers, long distance cables, smart meter

### Power Grid

(realtime) facts about actual instances of power grid assets:

- large batteries
- EV position + charging status [+ owner preferences]
- solar pannels + positionong (causes actual current production, implies future actual production) + measurement of current production rate
- wind parks + size & position
- public charging stations
- households: private charging stations, battery, solar, smart meter, washing machine, phone/laptop charger
- authentication of legal ownership, actual control, and produced measurements

## Power Market

- Map of regelzonen:
  - Germany
  - Austria
  - France
  - ...
- Current reserveleistungsanbieter: Primar, Sekundar, Tertiar
- Current total amount of registered trading accounts
- Current organizaional structures for each TSO (4 in Germany)

### Instances of exchanges

#### XBID

Remot order books for cross-zone and cross-border power trading, subject to available capacities in power grid.

#### EPEX

- Read only realtime intraday market information
- Trading in intraday markets
- Monitorig of intraday trading accounts

Todo:

- Dayahead markets
- Yearly markets

#### NordPool

## Geospacial Process

**individuals:**

physical embodyment of single living organisms. Can be linked to a virtual subject by means of authentication.

**things:**

physical body of a mechanical device. Can represent itself virtually as object with an embedded device, a MAC address, and networking capabilities. May expose an action space depending on the fuctionality of the thing. Can also expose measured sensory information if the thing captures any inputs like buttons or physical sensors.

**Moving through space:**

- subject
- instrument
- destination

**spacial causation:**

- distances
- speed of travel based on vehicle and road conditions
- fuel consumption
- sensing each other (being around, close to each other. e.g. Bluetooth)
- **interacting with each other: subject uses object as an instrument; subjects and objects have behavior over an action space. Acts of subjects and objects gives rise to causal influence over each other.**
- Authentication: Subjects and objects can authenticate themselves over a private key and some auth token. Like that of a location history in the SPS social graph

## Ride Sharing

- Cars spacial process: drivers, fuel consumption, positioning
- Navigation, street map, ETA estimation
- Driver hiring and work attribution (through car manufacturer API) plus driver interface
- Order process and rider interface
- Car management: parking, fueling, repairs
- Car ownership: Legal owner of the car
- Car position verification: manufacturer as trusted third party via API
- Payment process: Crypto, PayPal

## Subject Positioning System

Bluetooth gossiping to create a social graph of physical proximity between mobile devices, further assuming most people carry their phone with them, actively gossiping to their close neighbours.
