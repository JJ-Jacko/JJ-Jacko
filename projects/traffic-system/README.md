# Traffic System
## 📋 Description
Smart traffic light system for future human-centric and easy-to-manage streets
cuts 24/7 beeping noise by adapting sound levels to peak/off-peak hours. 
Web dashboard monitors clients (Raspberry Pi) remotely, logs every button press
and signal change, keeps working even when offline. 
It also exposes real-time signal data via APIs for mapping apps
and government, replacing algorithmic guesswork with ground-truth.

## Server (Control System)
* Platform: Web
* Feature:
    - Take over the heartbeat signal and real-time status of the clients.
    - Remote control the specific client status.
    - Reserve API to share the traffic light data for map and government.
    - Logging all of the clients.
        - Traffic light switching date time.
        - Pedestrians actively use crosswalk button.
* Technology stack:
    - Python
    - FastAPI
    - httpx
    - Nginx
    - Redis
    - PostgreSQL

## Client (Traffic Light)
* Platform: Raspberry Pi
* System: Linux
* Plugin: Internet module (IoT SIM card)
* Feature:
    - Normal feature of traffic light.
    - Accessibility sound (Reference street of Hong Kong).
    - Send the heartbeat signal and real-time status to the server.
    - Accessibility sound volume using the configration from server.
        - Distinguish high and low peak of traffic flow
            to control the affect of the noise.
        - Suddenly disconnect still running default.
* Technology stack:
    - Python
    - FastAPI
    - httpx
