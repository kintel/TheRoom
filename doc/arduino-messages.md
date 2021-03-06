# Intro

We're currently using the Arduino-SerialCommand library (https://github.com/kroimon/Arduino-SerialCommand).

We might change to JSON to simplify the router, e.g. using the aJson library:
https://github.com/interactive-matter/aJson

# Connection

Identify client: 
LOGIN <name>

Examples:
LOGIN Chambord
LOGIN Studio
LOGIN Cindy

NB! No spaces allowed

# Events

## Proximity

PROX <value>      # value is floating point cm, 0 means no presence

Examples:

// this is the default, also used to detect people leaving
PROX 0
// 23.5 cm
PROX 23.5
// Use this for on/off type proximity (presence)
PROX 1

## Knocking

o knock
o delay + knock
o knock pattern: starting with an optional delay, then a series of delays

Examples:
No initial delay: knock-knock-knock--knock
KNOCK 0 500 500 1000

Initial delay: -knock-knock--knock
KNOCK 500 500 1000

Shave&haircut call:
KNOCK 398 303 141 437

Correct shave&haircut answer:
KNOCK 1000 500

## Commands

CMD open_sesame
