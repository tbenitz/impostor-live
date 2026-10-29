# Impostor Live — TV + Phone Multiplayer Game

A live social-deduction party game: one TV/laptop hosts the shared map and scoreboard, while people join with their own phones by scanning a QR code. There are **no mock players**.

## Play online with GitHub Pages

1. In this repository, open **Settings → Pages**.
2. Under **Build and deployment**, select **Deploy from a branch**.
3. Select **main**, **/(root)**, then **Save**.
4. Once GitHub publishes the site, open **https://tbenitz.github.io/impostor-live/** on the main TV/laptop. Leave the host browser open.
5. On the TV, select **Join QR** and have everyone scan the QR code. Or share the join link.
6. Players enter their names on their phones. When at least 3 players have joined, set options and press **Start round**.

> The QR must lead to a publicly reachable HTTPS page. Opening `index.html` from a local `file://` path does not produce a usable cross-device QR link.

## Gameplay

- **Host / TV:** Large shared map with anonymous moving dots, QR/room code, scoreboard, player statuses, event feed, round controls, impostor count, map and timer settings.
- **Crewmates:** Privately assigned tasks at map stations, joystick or tap-to-move navigation, reporting bodies, emergency meetings, and voting.
- **Impostors:** Secret role, kill action with range/cooldown, and sabotage.
- **Meetings:** Discussion timer, private phone voting, ejection reveal, automatic win checks.
- **Late joiners:** Join as spectators and are automatically eligible for the next round.
- **Next rounds:** Freshly assigned roles with the same room and remembered session wins.

### Phone controls

Move with the virtual joystick, by tapping a location on the map, or with WASD/arrows on desktop. Approach an indicated task station and complete the three-switch console when available. Use the report/meeting action when eligible, or the kill/sabotage buttons if you're assigned as an impostor.

## Technology and limitations

- The game is shipped as one `index.html` file, with no backend deployment required.
- PeerJS and QRCode.js are loaded from CDNs; PeerJS Cloud handles signaling. Peer-to-peer game traffic uses WebRTC; it still requires an internet connection.
- The host browser maintains authoritative game state. The room goes away if the host closes or reloads the page.
- Restricted Wi-Fi, NATs and some mobile carriers may prevent direct WebRTC data connections because no TURN relay is included.
- This is a prototype with two map themes on a shared room layout; it isn't the original Among Us game.
- Recommended: 3–20 people, with sufficient crewmates for the number of impostors.
- Multi-device connections over external real-world networks still need verification; browser and local test-peer checks were performed during the prototype build.

## Files

- `index.html` — the complete host and phone experience

To update the game later, replace `index.html` and GitHub Pages will publish the changes automatically.
