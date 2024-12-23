# RadioRocketV2 📡🚀

RadioRocketV2 is an open-source project designed around the configuration and integration of amateur radio systems using modern digital tools into mid and high power model rockets. Built by N3VEM, with contributions from the community, this project empowers ham radio and rocket enthusiasts to combine their interest. 

This repository is based of the N3VEM version 2 of the radio rocket, code named Odori. 

This repository contains information related to version 2 of the [radio rocket project.](https://n3vem.com/rocket)

More specific details can be found in the readme within each folder, for the various components of the rocket and base station.

Please note that this repository isn't step-by-step directions. However, KC3ZTQ has updated the documentation to make it easier to follow along. If you are wanting to replicate this project, and have any questions, please feel free to reach out to N3VEM or KC3ZTQ. 

## APRS in the Rocket
APRS tracking is used in the rocket primarily for position data, mapping, and tracking. Track how high your rocket went, and how far away it's packets were received. The APRS sled can be done stand-alone without the rest of the project, if you simply want to beacon packets, and then check aprs.fi for data. Building the APRS tracker only would rely on their being at least 1 I-Gate within range of your launch site.

## LoRa & Telemetry in the Rocket
The rocket uses 70cm LoRa to send telemetry packets, relay messages, and respond to commands.

## Ground Station
The ground station is a single board computer, LoRa feather module, SDRplay Dongle, and all the associated wiring and power components, built into a project enclosure. It's primary purpose is to receive the LoRa and APRS data, and then act as a server to serve up that data via node-red and and a networked sound modem so that it can be displayed in a web browser and APRS client running on any other network connected device (a laptop, tablet, etc.)
