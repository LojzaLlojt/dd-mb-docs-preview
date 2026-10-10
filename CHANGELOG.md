# Changelog

All notable changes to this project will be documented in this file.

## [v26-10-10]

### Fixed

- Button graphics aligned in simplified end station.
- Removed "Ring" button for arriving train to simplified view.

### Changed

- Light theme reworked to increase contrast.

## [v26-09-09]

### Added

- Added possibility to alert adjacent station.
- Added possibility to load more trains in simplified end station.
- Added multiple-track (block) support between simplified hidden stations and adjacent stations, with a configurable default offering block in admin center.
- Added possibility to add another train and offer it in parallel when a multi-block section has spare capacity.
- Added driver assignment (from Rosters) and next station display in simplified hidden station, each toggled independently via the burger menu; shows "Unassigned" when no driver is assigned.

### Fixed

- "Removing" trains in simplified end station is now called "back" and functionality is restored.
- Clicking on "Back" button in simplified end station did not reset background color in adjacent station.

### Changed

- In simplified end station there is possibility to enable multiple languages at once.

## [v26-09-06]

### Changed

- Block & Train Color States: When an offered train is accepted, the block turns red while the train icon remains yellow. The train icon now turns red only after departure.

## [v26-08-29]

### Added

- Added rosters assignment for another day.
- Added driver statistics to rosters per roster and train drived (total and by type).

## [v26-08-28]

### Added

- Added password protection to remove train if not at terminus. Password is configurable from admin portal. Default is same to admin portal.
- Added rosters password hint for default password in admin portal.
- Added new sorting (accessible via burger menu) - "Active on top" with possibility of reorder active trains.

### Changed

- Extended model time speed to 10x.

### Fixed

- Fixed track number persistency.
- Fixed audio issues when browser process is suspended.

## [v26-08-14a]

### Fixed

- Routing trains via block 2 was not handled properly.
- Automatic hidden station now accepts train and clear blocks properly prior to removal from layout.

## [v26-08-14]

### Changed

- Dimmed "Actually in" stations.

### Fixed

- Translation error when adding extra train.

## [v26-08-13]

### Added

- Added version number to logon screen.

### Changed

- Rosters are sorted alphabetically in Rosters view.

### Fixed

- Fixed rosters import.

## [v26-08-12]

### Fixed

- When adding train next to automatic hidden station and train is confirmed as arrived block between hidden station and adjacent station is not being freed in dispatcher view for hidden station.

## [v26-08-11]

### Added

- Possibility to reorder blocks by drag & drop.

### Changed

- Changed a way how to report incomming and outgoing trains. Removed block arrow and changed to arrow from or into the station.
- Updated INSTALL.md.
- Expanded DISPATCHER.md.

### Fixed

- When added train from automatic hidden station and offered to adjacent station the currently operated station has no power to confirm arrival / departure.

## [v26-08-07]

### Added

- Install documentation.
- Added possibility to change default alert.

### Changed

- Default alert changed to "Default Alert1.mp3".

### Fixed

- Layout import did not prepopulate tracks.
- Added button to delete circulations.
- Fixed placeholder naming for circulations part in admin portal.

### Updated

- Install scripts.
