# Changelog

## [Unreleased]

### Fixed
- Fixed incorrect `hasOwnProperty` usage in network.ts (line 156 → 67)
  - Was accessing property instead of calling method: `networkInfo["hasOwnProperty"](key)`
  - Now correctly calls method: `networkInfo.hasOwnProperty(key)`
  - Impact: Prevents runtime errors and ensures default values are properly assigned
- Removed incomplete data-driven architecture pattern (89 lines) that broke network information display
  - Removed: NetworkConfig, NetworkSection, NetworkCommand interfaces
  - Removed: NETWORK_CONFIG, loadDataDriven(), renderDataDriven()
  - Impact: Restores all missing network sections in UI

### Changed
- Restored proper data loading with `loadNetworkData` (replaces broken `loadDataDriven`)
- Restored proper rendering with all render functions (replaces incomplete `renderDataDriven`)
- Improved code architecture by removing 95 lines and adding 46 (net: -49 lines)
- Updated .gitignore to exclude package-lock.json (project uses bun.lock)

### Improved
- All network sections now properly render:
  - Mobile Network (IP, Gateway, Device, WiFi/Data/Airplane toggles)
  - Wireless Information (SSID, BSSID, Signal strength, etc.)
  - Cellular Information (Operator, Network type, SIM details)
  - Network Capabilities (Routes, TCP buffers, MTU)
  - APN Information (Name, APN, Proxy, Authentication, etc.)
