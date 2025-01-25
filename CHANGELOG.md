# Changelog

## [4.7.21](https://github.com/Norgate-AV/RMS-SDK/compare/v4.7.18...v4.7.21) (2024-08)

### Prerequisites

- RMS Server version 4.8.3.1 or greater
- NX based controller (Controller Firmware v1.4.90 or greater)
- At least 64MB allocated to Duet memory

### Changes in this release

- Fixed the DVX Switcher's 'Internal Temperature' parameter issue, which was not reporting correctly in RMS
- Disabled the 'Track Changes' for the 'Fan Speed 1' and 'Fan Speed 2' parameters of DVX Switchers
- Fixed the Side LED flashing issue for Varia touch panels, when configured as RMS Scheduling Panels

### Known Issues

- If DVX Switchers(NCITE, DVX-HD or DVX-4K) were registered already with previous versions of NX RMS SDK (v4.7.20 or earlier),
  the registered 'Operating Temperature > 50°C' Parameter Threshold should be removed, as a new Parameter Threshold ('Operating Temperature > 70°C') will be registered.
- If Touch Panel or DVX devices were previously registered with NetLinx monitoring modules, the registered control methods should be removed before registration of new devices. Any control macros referencing the removed control methods will need to be updated.

## [4.7.18](https://github.com/Norgate-AV/RMS-SDK/compare/v4.7.18) (2021-10-12)

### Prerequisites

- RMS Server version 4.8.0 or greater
- NX based controller (Controller firmware v1.4.90 or greater)
- At least 64MB allocated to Duet memory

### Changes/Fixes in this release

- Server password is encrypted in the `rms.properties` file of RMS module, when loaded on NX Controller
- Increased the lamp consumption maximum value to 25000 for the Video Projector(from 2000) and Document Camera(from 5000)
- Added support for the following devices:
    - DVX-3266-4K
    - DVX-2265-4K
    - DX-RX-4K60
    - DX-TX-4K60
    - DXFP-RX-4K60
    - DXFP-TX-4K60

### Changes in previous release

- Fixed the ControlSystemMonitor and PowerMonitor reporting issue that got broken
- Fixed the registration issue, when two devices share the same DPS
- Support added for the following devices:
    - Acendo Core (ACR-5100)
    - VPX Switchers (VPX-1401/VPX-1701)
    - INCITE Switchers (NCITE-813/813A/813AC)
    - Modero G5 Touch Panels( MT-2002/MT-1002/MD-1002/MT-702/MD-702)
- Fixed Issue ESC 32133:- Next Appointment Info on touch panel is not getting cleared when it should.
- Improved response time for scheduling create, extend, and end requests
- Added auto registration support for Touch Panels, HydraPort Touch Panels, DVX and DGX
- Added additional auto registration capabilities for DXLink(does not include Wallplate devices) and Solecis
- Corrected an issue which could lead to excessive logging
- Various other bug fixes and improvements

### Known Issues

- If Touch Panel or DVX devices were previously registered with NetLinx monitoring modules,
  the registered control methods should be removed before registration of new devices. Any control
  macros referencing the removed control methods will need to be updated
