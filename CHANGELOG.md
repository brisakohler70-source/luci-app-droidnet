# Changelog

## [Unreleased]

### Fixed
- Fixed incorrect `hasOwnProperty` usage in network.ts that could cause runtime errors
- Removed incomplete data-driven architecture pattern that broke network information display

### Changed
- Restored proper data loading and rendering for all network sections
- Improved code architecture by removing 85 lines of unused/incomplete code
- Updated .gitignore to exclude package-lock.json (project uses bun.lock)

### Improved
- All network sections now properly render: Mobile Network, Wireless Information, Cellular Information, Network Capabilities, and APN Information
