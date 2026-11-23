# Bluetooth Priority for Windows

Bluetooth Priority is a Windows system tray app for choosing your preferred headphones, speakers and microphone, adjusting their volume, and managing paired Bluetooth audio connections. Put your headset before your desk speakers to switch back to the headset automatically when it reconnects.

**[Download Bluetooth Priority 1.1.11 for Windows x64 (portable ZIP)](https://github.com/istvanvass982-tech/Bluetooth-Priority/releases/download/v1.1.11/BluetoothPriority-1.1.11-portable-win-x64.zip)** · [Release notes and checksum](https://github.com/istvanvass982-tech/Bluetooth-Priority/releases/tag/v1.1.11)

Saved you a trip to Windows sound settings? [☕ Buy me a coffee](https://ko-fi.com/istvanv) · [Tip via PayPal](https://paypal.me/foliazo)

[Playback outputs](#playback-outputs-and-priority) · [Microphones](#microphones-and-recording-inputs) · [Volume shortcuts](#volume-mute-and-shortcuts) · [Bluetooth connections](#bluetooth-connections-and-battery)

## Getting started

1. Extract the **entire ZIP** to a writable folder and run **BluetoothPriority.exe**. The Windows x64 package includes its runtime.
2. Click the notification-area icon to open or hide the panel. Right-click it for the tray menu.
3. Arrange playback devices from most to least preferred. Drag a row, choose its numbered position, or use **Alt + ↑ / ↓** on a focused row.
4. Click an available device to select and pin it. Click it again, or choose **Restore automatic selection**, to resume automatic playback selection.

The app starts in English. Hungarian is available in Settings or the tray language menu. Escape or a click outside the panel normally hides it. The app keeps running until you choose **Exit** in the tray menu.

## Playback outputs and priority

The main **Bluetooth Priority** view is the editable playback priority list. It also supports Windows playback endpoints such as USB audio, built-in speakers and HDMI/display audio. Disconnected devices can stay visible so you can arrange their saved positions.

- Automatic mode chooses the highest available device in the saved order. A **Fallback output**, if configured, is used only when no other ranked output is available.
- A manual pin overrides the order. If that endpoint disconnects, the app can use an available endpoint belonging to the same device, then fall back through the order. The pin remains so the preferred endpoint can return when available.
- **Pause / Resume** in the tray controls playback switching. Resume restores automatic selection and clears the pin.
- Playback selection sets and verifies all three Windows default roles (console, multimedia and communications). A short settling delay helps avoid switching during a connection change. Repeated switching conflicts or failures can pause automatic selection.
- Optional **Switch notifications** report successful playback changes.

The **All audio outputs** view shows currently available outputs in a compact list with Bluetooth devices first in their saved priority order, followed by other outputs ranked by observed playback use. This view does not rewrite your saved priority order. Click a device to pin or unpin it just as in the main view.

## Microphones and recording inputs

Use **Show inputs** to open the separate **Inputs** view. It lists available recording devices, their default status and whether Windows reports them in use. It observes recording-session activity without opening a recording stream itself.

Inputs initially follow a usage-based order. Drag, select a numbered position, or use **Alt + ↑ / ↓** to create a custom input order. **Restore usage order** removes that custom ordering. Playback and input ordering are independent.

Click an input to set all three Windows recording default roles and pin it. Click the pinned input again to release it and let the highest-ranked available input become the default. After input selection is activated, a disconnected pinned input falls back to the ranked available inputs and can return on reconnection. An **Unpin input** button is available if the pinned device disappears from the list.

At startup, the input view observes and ranks devices without automatically changing the recording default. Selecting or releasing an input activates input selection for that run. Reordering alone does not activate it. Input and playback pins are temporary. The saved orders and usage history persist.

### Microphone gain and Equalizer APO

Click an input's **dB** value to open its gain controls. Use **− / +** to change the value and **Undo** to reverse the last adjustment when the value has not changed elsewhere. The label tells you which control is available.

| Label | What it controls |
| --- | --- |
| **Preamp · Equalizer APO** | An existing supported capture preamp profile for that input. |
| **Microphone gain** | A separate gain control exposed by the device/driver. |
| **Input level · Windows** | The Windows input volume expressed in dB when separate gain is unavailable. |

Equalizer APO support requires an existing installation attached to the input, enabled effects, and a matching simple `config.txt` profile containing one `Device`, `Stage: capture`, and `Preamp` setting. Supported preamp adjustment is **−30 to +30 dB**, in **1 dB** steps. The app does not install or configure Equalizer APO and does not edit arbitrary multi-device or filter-chain profiles. Hardware gain ranges depend on the driver. Unavailable controls show an explanation instead of an adjustable value.

## Volume, mute and shortcuts

The panel's top bar controls the current default output, or the current default input while the Inputs view is open. Use the **0–100% slider**, percentage readout and **mute/unmute** button. In an output or input view, hold **Ctrl** and scroll with the mouse wheel or a two-finger touchpad gesture to adjust that view's volume.

Global shortcuts work while the panel is closed and target either output or input volume.

| Action | Default |
| --- | --- |
| Volume up / down | **Ctrl + Shift + wheel up / down** |
| Switch volume target between output and input | **Ctrl + Shift + F10** |
| Next playback output | Choose a shortcut to enable |

Opening an output or input view also selects that global volume target. The tray's **Settings → Volume target** item switches it. **Next output** cycles available playback endpoints in priority order and pins the selected output.

In **Settings → Edit shortcuts…**, add, replace or remove keyboard and wheel combinations, save your edits, or restore the defaults. An action can have multiple alternative combinations. Each combination needs at least one modifier and can belong to only one action. A shortcut already reserved by another app may be unavailable. Choosing a common gesture such as **Ctrl + wheel** also takes over its usual function in other apps, such as browser zoom.

Settings let you enable or disable global volume shortcuts and quick input/output switching, and choose **Normal** or **Inverted** volume scrolling. The quick-switch setting also controls the Next output shortcut.

### On-screen volume display

Global volume changes and target switching show an on-screen display with the device name, input/output target, level and mute state. Click the device name to choose another available device directly. The display stays open while you interact with its picker. Set its duration to **1.25, 2.5, 4 or 6 seconds**. The default is **2.5 seconds**.

## Bluetooth connections and battery

Open **Connections** to see paired Bluetooth audio devices, including whether they are merely paired, linked over Bluetooth, or connected for audio. Devices are ordered using observed playback activity. Use **Connect** or **Disconnect** to request an audio connection change. Compatible device rows in the main priority view also expose these buttons.

Battery percentages and battery-coloured tiles appear when Windows and the device expose a usable reading. Connection controls require a Windows audio profile. **Pair a device in Windows** opens Windows Bluetooth settings for pairing.

Connection requests depend on Windows, the Bluetooth driver and the headset. A headset that is off or held by another computer may need attention there before it can connect. The app cannot guarantee battery reporting or connection control for every device.

## Settings, editions and updates

Choose **System**, **Light** or **Dark** theme. The panel also follows Windows high-contrast colours. Other settings include showing disconnected playback devices, switch notifications, fallback output, language and shortcuts. On a fresh configuration, disconnected playback devices are shown, switch notifications are off, no fallback is selected, and the theme follows Windows.

| Edition | Preferences and startup |
| --- | --- |
| **Portable ZIP** | Stores preferences in the **Data** folder beside the executable, opens the panel on launch, and does not offer Start at sign-in. Keep the app in a writable folder. |
| **Non-portable build** | Stores preferences under **%LOCALAPPDATA%\Bluetooth Priority\Live** and offers **Start at sign-in** in Settings. |

Only one instance can run in a Windows session, including across editions. Exit the running copy before opening another. To update the portable edition, choose **Exit**, extract the new package, and retain your **Data** folder. The two editions use separate preference locations.

## Limits and troubleshooting

Volume and device controls operate on Windows default endpoints. Applications with their own selected input/output may need to be set to **System default**, and some applications may need their audio session restarted after a switch. Playback Pause does not disable microphone selection or global volume shortcuts.

Device availability, microphone gain, battery readings and Bluetooth control depend on what Windows and the driver report. If automatic playback switching pauses after a failure or competing default-device changes, check the panel status and device availability, then use **Restore automatic selection** when ready.

## Support and feedback

Optional tips are available from the tray's **Leave a tip… → Ko-fi / PayPal** menu and from Settings. All features are available without a donation.

For a device-switching or shortcut problem, include the app version, Windows version, device model, what you expected and what happened. [Report an issue](https://github.com/istvanvass982-tech/Bluetooth-Priority/issues)
