# Installing from LogicalCube Fork

This fork includes additional features and improvements beyond the upstream version:

- ✅ Server-Sent Events for real-time browser updates
- ✅ Verbal approval system with pre-tool hook for voice mode safety
- ✅ Security vulnerability fixes (all 8 vulnerabilities patched)
- ✅ Pre-tool hook bug fixes (no false positives)
- ✅ All 127 tests passing

## Quick Install

```bash
# Install Claude Code (if not already installed)
npm install -g @anthropic-ai/claude-code

# Add voice-hooks from LogicalCube fork
claude mcp add voice-hooks npx LogicalCube/mcp-voice-hooks

# Install hooks
npx LogicalCube/mcp-voice-hooks install-hooks
```

## Usage

```bash
# Start Claude Code
claude
```

The browser interface will automatically open at http://localhost:5111 after 3 seconds.

Click "Start Listening" to enable voice input.

## Features

### Server-Sent Events
Real-time updates from the server to the browser. The UI now shows when Claude is waiting for your voice input without polling.

### Verbal Approval System
The pre-tool hook enforces safety in voice mode:
- **Deny**: Destructive operations (rm -rf, git reset --hard, etc.) always require approval
- **Ask**: Non-allowlisted tools require approval
- **Allow**: Allowlisted safe operations proceed automatically

All decisions are logged to `~/.mcp-voice-hooks/audit.log`

### Security
All npm dependencies updated with zero vulnerabilities.

## Differences from Upstream

This fork is based on [johnmatthewtennant/mcp-voice-hooks](https://github.com/johnmatthewtennant/mcp-voice-hooks) with the following additions:

1. **SSE Implementation** - Real-time server-to-browser communication
2. **Pre-Tool Hook** - Intelligent safety system for voice mode
3. **Security Patches** - All vulnerabilities fixed
4. **Enhanced Tests** - 127 tests (up from 86)

## Development

To work on this fork locally:

```bash
# Clone the fork
git clone https://github.com/LogicalCube/mcp-voice-hooks.git
cd mcp-voice-hooks

# Install and build
npm install
npm run build

# Link for local development
npm link

# Install hooks
npx mcp-voice-hooks install-hooks

# Start Claude Code
claude
```

## Pull Request

These improvements have been submitted to upstream via [PR #7](https://github.com/johnmatthewtennant/mcp-voice-hooks/pull/7).

## Support

For issues specific to this fork, please open an issue on the [LogicalCube fork](https://github.com/LogicalCube/mcp-voice-hooks/issues).

For upstream issues, see the [original repository](https://github.com/johnmatthewtennant/mcp-voice-hooks).
