# 1.0.0 - 2026-10-30

First release of Quintessential for Minecraft Beta 1.7.3.

## Features

### Social
- Add friends by username and see who's online.
- Click a friend in the Social screen to open your DM with them.
- Accept friend requests directly in Social.
- Session invites arrive as a single line in the conversation - **Click this to join the session** - with an Accept button. No addresses to copy and no server list.
- Messages and invites appear as quiet toasts, so nothing interrupts the game.

### Wardrobe
- Import 64x32 or 64x64 PNG skins and equip them instantly.
- Preview skins on a rotating player model.
- Skins are shared with other Quintessential players on the same server.

### Host World
- Host one of your singleplayer saves for up to 8 players.
- Starts a real Beta 1.7.3 server on a copy of that save and connects you straight into it.
- The server jar is downloaded once from the public BetaCraft archive and verified against a known SHA-1 hash. It is never bundled with the mod.
- Direct hosting: forward the chosen port on your router. No relay service and no hidden NAT traversal.

### Pictures
- Browse your screenshots and take new ones without leaving the game.

### Account (optional)
- Sign in with your Microsoft account through Microsoft's official device-code flow to upload a wardrobe skin to your real Minecraft profile.
- Optional; no other feature needs it.

### Settings
- Toggle notifications, sounds, pause-menu buttons, and the join hint.
- Choices are saved automatically.

### Interface
- Black and grey panels with an amber accent on the title screen, pause menu, and the **K** menu.
- Works on the official obfuscated Beta 1.7.3 client and on MCP development workspaces.

## Fixes

- Hosting no longer hangs on **Logging on**. The client's fallback handshake was sent as a chat line longer than Beta's 100-character limit and raced the server's mod marker, so the server disconnected with *Chat message too long*. Social traffic now waits for the server marker and only travels in the dedicated packet.
- The "this server runs Quintessential" flag is no longer cleared while the hosted world finishes loading.
- Server-side classes are reobfuscated for the official server jar, so custom packet registration and player tracking work on hosted worlds.
- Hosted worlds are only joined after the server prints its "Done" line and actually accepts connections.
- The invisible-chat fallback was removed. Beta servers reject the section sign and long lines, so it could only ever get players kicked; unmodded servers now simply see nothing.

## Notes

- Requires **Java 8**; Beta 1.7.3 does not run on newer Java versions.
- Installed as a Java agent with `-javaagent:`; no game files are modified.
- Vanilla clients can join a hosted world normally, they just miss the extra features.
- Remove the `-javaagent` argument to uninstall.
