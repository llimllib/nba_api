# NBA API Change Log

## About Versioning

- The NBA API uses [Semantic Versioning 2.0.0](https://semver.org/)
- Dates are [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) compliant and formatted as `YYYY-MM-DD`

### Types of changes

- `Added` for new features.
- `Changed` for changes in existing functionality.
- `Deprecated` for soon-to-be removed features.
- `Removed` for now removed features.
- `Fixed` for any bug fixes.
- `Security` in case of vulnerabilities.

# Version History

## v1.1.12

Date: 2022-10-11

### Added

- 2022-10-08 [Player Data]([https://github.com/swar/nba_api/blob/master/nba_api/stats/library/data.py](https://github.com/swar/nba_api/blob/master/src/nba_api/stats/library/data.py))
- Endpoints
  - [VideoEventsAsset](https://github.com/prateekjaipuria/nba_api/blob/master/nba_api/stats/endpoints/videoeventsasset.py) ([#259](https://github.com/swar/nba_api/pull/259) - [prateekjaipuria](https://github.com/prateekjaipuria))
- [`CONTRIBUTING.MD`](https://github.com/swar/nba_api/blob/master/CONTRIBUTING.md)
- [`CHANGELOG.MD`](https://github.com/swar/nba_api/blob/master/CHANGELOG.md)
- GitHub issue template for bugs
- CircleCI build support for Python 3.10
- pyproject.toml ([PEP 621](https://peps.python.org/pep-0621/))

### Changed

- CircleCI
  - [Migrated to next-gen Convenience Images](https://circleci.com/docs/next-gen-migration-guide/)
  - [Config to Version 2.1](https://discuss.circleci.com/t/circleci-2-1-config-overview/26057)
  - Moved `flake8` and `pytest` into Commands
  - Parameterized docker images
- README.md
  - Link to [NBA.com Terms of Use](https://www.nba.com/termsofuse)
  - Getting started samples at the top
  - Other edits for improving the reading structure
- Project Structure
  - Source code moved from flat-layout to src-layout
  - Tests were divided into Unit/Integration

### Removed

- Support for Python 3.4, 3.5, and 3.6
- Setup.py file in favor of pyproject.toml ([PEP 621](https://peps.python.org/pep-0621/))

### Fixed

- [Issue #249](https://github.com/swar/nba_api/issues/249): `./nba_api/stats/endpoints/_base.py` requires `numpy` to format data for `get_data_frame`. `numpy` was not in the list of requirements, but is required.
- [Issue #278](https://github.com/swar/nba_api/issues/278): Fixed `playbyplayregex`, and included updated unit tests, where
  - The NBA removed a space that represented `distance` when `distance` was not included in the made/missed shot.
  - Jump Ball contained a single space in the description (regex now also supports multiple spaces empty description).
  - Team fouls no longer included Player/Referee, just the Team Name & Foul.

## v1.1.11

Date: 2021-11-8

- Merge pull request #231 from swar/live

## v1.1.10

Date: 2021.10-31

- Merge pull request #212 from baronet2/master
- Merge pull request #219 from edlavairee/find-teams-by-championship-year
- Merge pull request #226 from mjstamper/master
- Merge pull request #184 from rsforbes/live
- updated latest data.py from master
- changed prev_season to previous_season
- Merge pull request #1 from mjstamper/prev_season_add
- Added previous season to the Season parameter
- Merge pull request #225 from swar/static-data-update
- Added new feauture: User can now find the team who won a championship title for a given year.
- Added level names for MultiIndex columns of DataSet
- Add handling of multiple level column names in DataSets
- rolling back notebook changes
- removed .vscode/launch.json
- Updated Live Data Notebook
- undoing fix
- fixed references in tests for 3.4
- finilized testing and documentation for BoxScore
- Updated test for 3.4 & 3.5 backwards compatability
- Added AlwaysPresent to playbyplay.md
- Updated info on playbyplay.md
- major updates for live data (playbyplay, boxscore, and scoreboard)
- Merge pull request #7 from rsforbes/player_data_file
- Updated data.py with current player data
- Merge pull request #187 from rsforbes/playbyplay
- Merge pull request #188 from rsforbes/version_update
- Merge pull request #192 from rsforbes/gitignore_upd
- removed .vscode as it's in .gitignore and should have been checked in
- Adding Python 3.8 & 3.9 to the build
- further separated stats from live by moving over _base.py and having live endpoints reference that
- added fully working examples of live data in  docs/examples/PlayByPlay_Live.ipynb
- reverting nba_api/status/library/http.py to original
- updated live/endpoits/__init__.py to include new endpoints.
- updating live files for further review
- Fixed two issues. First, was not handling multiple in timeout_type. Second, new team violation type has been added by NBA.
- Live Data
- missed library for http.py
- adding in a new 'live' endpoint on s3 with libraries around playbyplay data. This will allow resutls during a live game

## v1.1.9

Date: 2020-01-27

- Updating table of content
- Adding test for LeagueDashOppPtShot
- Reverting more changes
- Changing to quotes
- Mistakenly pushed
- Merge pull request #152 from justinbt21/patch-1
- Adding 21 new endpoints with minor fixes to accommodate
- Removing TeamGameStreakFinder from tests
- Adding HustleStatsBoxScore endpoint
- Fixing link to requests
- Updates after re-run of analysis
- Updating documentation for analysis tool
- Printing proxy on DEBUG
- Upgrading endpoint analyzer
- Update __init__.py with LeagueDashOppPtShot
- Adding Questions and Help section

## v1.1.8

Date: 2020-01-27

- Forgot to remove debug code... this is why you don't program when you should be sleeping

## v1.1.7

- Forgot to add new endpoint on second section of __init__

## v1.1.6

- Updated Analysis
- Updated Endpoints and Parameter py files and docs
- Added Parameter Overriding
- Added new endpoint: TeamGameLogs
- Updating Static Player Data
- Updating error values
- Updating headers
- Adding proxy list support for randomization
- Merge pull request #115 from Mathiasme/patch-1
- typo

## v1.1.5

Date: 2019-11-09

- Adding new test: PlayerGameLogs
- Conforming to PEP8
- Conforming to PEP8
- Adding PlayerGameLogs to import
- Adding PlayerGameLogs
- Merge pull request #89 from rsforbes/master
- Updating static data
- Updating analysis.json
- Updating stats endpoint documentation
- Updating stats endpoints
- Updating parameters.md
- Adding new parameter mapping: MeasureTypePlayerGameLogs
- Adding new mappings for OppTeamID and MeasureType
- Adding new endpoints: PlayerGameLogs
- Changing is to == operator
- Updating Development Version
- Adding updated default headers
- Adding debug folder to gitignore
- Fixed bug where referee not included in playbyplay violation
- Fixed bug where referee did not appear in foul.
- Fixed the issue with Mark Morris in playbyplay using new variable
- simplified all playbyplay regex with the exception of pattern_turnover_player
- Fixed a but in playbyplay regex where Timeout now has 'Reg.' for Full Timeouts
- Merge pull request #82 from davidbobyang/master
- Fixed description in stats/library/http.md

## v1.1.4

Date: 2019-04-28

- Adding create static data file script
- Merge pull request #70 from rsforbes/master
- Merge pull request #67 from TK05/development/static-files-tools
- updated play by play tests, test data, and added new integration test to validate previous days play by play data.
- Update static players list
- Refactored tool to use existing endpoint

## v1.1.3

Date: 2019-04-21

- Merge remote-tracking branch 'origin/master'
- Removing tools folder from PyPi build
- Merge pull request #66 from TK05/development/active-players
- Merge pull request #65 from TK05/hotfix/py-generator
- Merge pull request #64 from rsforbes/master
- New tool to update static data
- Updated data doc with new feature
- Fixed typo
- Updated docs with new player features
- Added active status to static players list
- Fixed bug in py file generator
- Added PlayByPlay Ejection Regex. Moved test data out of test_playbyplayregex to conftest.py. Added additional regex unit tests. Moved tests into PlayByPlay folder
- Merge pull request #62 from TK05/master
- Cleaned up unnecessary leftovers

## v1.1.2

Date: v1.1.2

- Updating parameter mapping
- Updating deferred endpoint test list
- Updating stats endpoints
- Updating parameters documentation
- Updating endpoint documentation
- Updating analysis.json
- Merge branch 'TK05-develop/synergy' Merging with master
- Merge branch 'develop/synergy' of <https://github.com/TK05/nba_api> into TK05-develop/synergy Merging TK05-develop/synergy new endpoint
- Merge pull request #59 from rsforbes/master
- Added known parameters for SynergyPlayTypes endpoint
- Updated docs for SynergyPlayTypes endpoint
- Updated analysis.json with SynergyPlayTypes endpoint
- Added SynergyPlayTypes to tests
- Added SynergyPlayTypes endpoint with needed parameters
- Added endpoint and mappings for synergyplaytypes
- Removed errant import statment in test_playbyplayregex. Renamed TestPlayByPlay to TestPlayByPlayRegex.
- renamed EventMsgType.FREE_THROW_ATTEMPT to FREE_THROW
- Added ^ to regex beginning of pattern_free_throw. Included new eventmsgtype Enum
- Adding Tests to CircleCI
- Added support for VS Code w/ .gitignore update
- cleaned up playbyplay regex and added tests
- cleaned up playbyplay regex and added tests
- cleaned up playbyplayregex and included tests
- Merge branch 'master' of <https://github.com/swar/nba_api>
- Merge pull request #5 from rsforbes/dev
- Updated playbyplay_regex
- Merge pull request #55 from eswan18/pytest2
- Switch random wait generator from numpy to random
- Update readme to explain running tests
- Break endpoint tests into multiple files.
- Convert EndpointTester to class.
- Finish reorg of test_endpoints; make it work.
- Reorganized test_endpoints more.
- Update test_endpoints to be neater.

## v1.1.1

Date: 2019-04-07

- Reverting headers
- Updating README

## v1.1.0

Date: 2018-12-11

- Updating basic examples to show support for individual proxy, header, and timeout settings
- Updating endpoints with new analysis and template
- Updating documentation with new analysis
- Adding another missing required parameter
- Updating tests
- Updating analysis.json
- Adding more missing required parameters
- Updating headers
- Sorting parameters
- Sorting parameters
- Updating nullable parameter matches
- Updating parameter documentation
- Updating analysis.json
- Updating get_parameters method to return null on invalid json
- Updating with individual proxy, header, timeout, and url generation support
- Adding newly identified parameters
- Adding endpoints and new mappings
- Adding base changes for proxies, headers, timeouts, and url generation
- Updating with exceptions when missing any mappings
- Updating for endpoint changes and more nullable parameter tests
- Merge pull request #52 from rsforbes/master
- Merge pull request #4 from rsforbes/dev
- updated playbyplay_regex with .format() for backwards compatability
- Merge pull request #51 from rsforbes/master
- Merge pull request #3 from rsforbes/dev
- Revert "Added playbyplay data"
- including playbyplay_regex for playbyplay & playbyplayv2 VISITORDECRIPTION & HOMEDESCRIPTION fields
- Merge pull request #2 from rsforbes/dev
- Added playbyplay data
- Merge pull request #46 from eswan18/readme-dev-instr
- Update readme; add development instructions.
- Updating version log
- Updating development version
- Merge pull request #45 from eswan18/tabcomplete-endpoints
- Merge pull request #44 from rsforbes/master
- Make tab-complete work on nba_api.stats.endpoints.
- Cleaned up PlayByPlay book fixing Regex as well as fixed a bug in getting Home & Visitor Descriptions
- Merge pull request #39 from rsforbes/master
- Added Jupyter Play by Play Notebook
- Merge pull request #29 from Hoax5547/master
- Update teams.md
- Merge pull request #28 from Hoax5547/master
- Fixed description in teams.md
- Another minor formatting change for #19
- Updating Endpoint Documentation Generator with minor formatting changes for #19

## v1.0.7

Date: 2018-12-11

- Updating tests and DefenseHub doc
- Updating Endpoint Documentation Generator for #19
- Updating endpoints with new parameters from 2018-12-11 analysis json
- Updating documentation for #19
- Updating analysis archive to 2018-12-11
- Removing unnecessary doc
- Merge pull request #22 from eswan18/master
- moved examples link in readme to the Usage Examples heading
- moved examples to docs folder and updated readme
- slight cleanup of example notebooks
- adding examples folder

## v1.0.6 commit

Date: 2018-10-11

### Fixed

- Disabled DEBUG Mode that was enabled by default in v1.0.5

## v1.0.5 commit

Date: 2018-10-10

- Adding LeagueDashPtStats to tests and __init__
- Updating version log
- Switching default values
- Adding LeagueDashPtStats Endpoint
- Changing last_validated to last_validated_date
- Adding last validated date to analysis JSON
- Adding build badge, minor edits to badges
- Merge pull request #9 from cclauss/patch-1
- Typo
- Merge pull request #8 from cclauss/patch-1
- Drop legacy Python
- CircleCI: Add some automated testing

## v1.0.4

Date: 2018-09-25

    - Updating README urls

## v1.0.3

Date: 2018-09-25

- Updating stats examples
- README changes and removing index.md

## v1.0.2

Date: 2018-09-17

- Updating with PyCharm and Debug Files
- Escaping vertical bar character from endpoint documentation

## v1.0.1

Date: 2018-09-17

## v1.0.0

Date: 2018-09-16

- Initial commit
