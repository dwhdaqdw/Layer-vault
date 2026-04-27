# LayerVault Pro No-License Build

LayerVault Pro is an Adobe After Effects ScriptUI panel for saving layers as reusable JSON presets and rebuilding them later in another composition.

This v1.5 release is the no-license build. It opens directly, does not require activation, and stores presets and settings in the user data folder.

made by @MythVfxx

## Overview

LayerVault Pro is built for presets that need to preserve more than a simple look. It is designed to carry over full layer setups, including transforms, keyframes, effects, expressions, masks, shape contents, text animators, switches, timing, and layer relationships.

## What's New In This Build

New in v1.5:

- Presets now load above the layer you have selected, instead of always jumping to the top of the comp.
- Added optional visual previews for compatible color-style presets.
- Preview controls only show up for compatible color tags, so the feature stays focused and does not clutter every preset.
- Eligible presets can now use attached thumbnails or capture a preview directly from the active comp.
- Added a preset thumbnail manager with `Replace`, `Clear`, `Reveal`, and `Capture Preview` actions.
- Added a `Capture Preview` shortcut for grabbing previews faster.
- Added a larger preview viewer with `Open External` support.
- Added a `Show previews` toggle so users can keep the panel compact unless they want visual previews.
- Added a new `Health Check` diagnostic report.
- Added a new `Selection Snapshot` report for selected layers.
- Added recovery log support with `recovery-log.txt`.
- Added `Open Recovery Folder` for easier crash follow-up.
- Missing plugin warnings now name the missing effect so users know what plugin is required.
- Improved the built-in troubleshooting and support workflow.
- Cleaned up the action layout into clearer `Main`, `Utilities`, and `Support` groups.

## What The Script Saves

LayerVault Pro is designed to preserve as much meaningful layer state as possible, including:

- transforms and transform keyframes
- effects and effect keyframes
- expressions
- masks
- shape layer contents
- text layer settings
- text animators
- blending modes
- layer switches
- timing data
- parenting relationships
- track matte relationships
- layer styles
- saved layer order metadata

Supported layer types in this build include:

- text
- shape
- solid
- null
- adjustment
- camera
- light

## Shape Layer Support

This build is intended to preserve full shape layer content, including:

- paths
- strokes
- dashed strokes
- gradients
- trim paths
- repeaters
- merge paths
- offset paths

## Main Features

### Save Preset

Save selected layers from the active comp into a named preset file.

The status area reports progress while the preset is being written.

### Apply Preset

Apply the selected preset back into the active composition.

If you have a layer selected in the timeline, LayerVault Pro inserts the restored preset directly above that selected layer instead of always sending it to the very top of the comp. If nothing is selected, it falls back to the top-of-comp behavior.

You can also select multiple presets and apply them in list order.

### Save Group

Save multiple layers as one grouped preset so they can be restored together in stored order.

### Preset Library With Folders

The library supports folders inside the preset area. You can:

- create folders
- move selected presets into folders
- open folders directly from the list
- move back up a folder level from the list
- delete folders and everything inside them

### Search, Favorites, And Tags

The library supports:

- live search filtering
- favorited presets pinned by star state
- tag summaries in the preset details area
- a `Show tags` toggle in the panel

### Restore Modes

Three restore modes are available:

- `Full Load`: restores the full preset behavior wherever possible
- `Safe Restore`: restores more cautiously and disables restored expressions
- `Safe Restore (No Expressions)`: skips expression restoration entirely

This is useful when moving presets between projects that do not have identical environments.

### Place At Current Time

The `Place at current time` option shifts the restored result so the earliest saved in-point lands on the current playhead while preserving the internal timing relationship between restored layers.

### Transfer Presets

Preset files are standard JSON. You can import them into the library or export selected presets for sharing.

### Preset Previews

Preset previews are optional and are designed specifically for presets where a still image is actually useful.

That is why previews are limited to compatible color-style tags instead of being available for every preset in the library. A thumbnail makes sense for things like color correction, grades, LUT looks, exposure changes, and overall tone. It usually does not help much for text animation presets, shake presets, transition presets, or utility presets where the important part is movement, timing, or behavior rather than a single frame.

Compatible preview tags in this build are:

- `Color`
- `Color Correction`
- `Grade`
- `Look`
- `LUT`
- `Exposure`
- `Tone`

A preset only becomes preview-compatible when it has one of those tags. If it does not, the thumbnail controls stay hidden so the panel does not show preview actions that do not really make sense for that preset type.

Why previews are limited to these tags:

- it keeps the feature purposeful instead of turning every preset into a thumbnail card
- it avoids misleading previews for presets where a still image does not represent the real result well
- it keeps the docked panel cleaner and easier to browse
- it makes the feature feel more useful for look presets instead of becoming random visual clutter

How previews work:

- tag a preset with one of the compatible color-style tags
- turn on `Show previews` if you want preview controls visible in the main panel
- use `Thumb` to open the preset thumbnail manager
- from the thumbnail manager, you can attach or replace a still image, clear the current thumbnail, reveal the thumbnail file, or use `Capture Preview` to grab a preview from the active comp
- use `Preview` to open the larger preview viewer
- use `Open External` from the preview viewer if you want to inspect the image in your system image viewer

### Why There Is A Show Previews Toggle

The panel includes a `Show previews` toggle because previews are meant to be optional, not forced into the main workflow for every user.

Some people will love having visual previews for color presets. Other people will want the smallest possible docked panel and may never use previews at all.

The toggle exists to:

- keep the main UI compact by default
- let users opt into previews only when they actually want them
- prevent preview controls from taking up space in tight docked layouts
- make sure the panel still feels fast and clean for users who only care about saving and applying presets

If `Show previews` is off, preview controls stay hidden even for compatible presets. This is intentional and helps keep the panel uncluttered.

### Diagnostics And Recovery Tools

The panel includes built-in troubleshooting tools:

- `View Logs`
- `Export Logs`
- `Clear Logs`
- `Debug Snapshot`
- `Health Check`
- `Selection Snapshot`
- `Open Recovery Folder`
- `Transfer Help`
- `Inspect Preset`

When something only partially restores, the logs and diagnostics are meant to show what failed and why.

### Recovery Log

LayerVault Pro keeps a recovery log file in the user data folder while the script runs.

This is designed to help after a crash or unexpected failure. If After Effects closes unexpectedly, the script cannot guarantee a last-second crash report, but it does keep writing recent log activity to `recovery-log.txt` while the script is running.

That means there is usually a recent on-disk log available to inspect after reopening After Effects.

### Shortcuts

The `Shortcuts` panel lets you customize shortcuts for:

- Save Preset
- Save Group
- Apply / Quick Apply
- Capture Preview

Default shortcuts:

- `Ctrl+S`
- `Ctrl+G`
- `Ctrl+Enter`
- `Ctrl+Alt+P`

### Appearance

The `Appearance` dialog lets users adjust panel colors and save those choices between sessions.

### Contact

The script includes a `Contact` button that opens the built-in support dialog.

## Main Panel Actions

### Main

- `Apply Preset`: apply the selected preset or preset selection
- `Refresh`: reload the preset library from disk
- `Save Preset`: save the current selected layers as a preset
- `Delete`: delete selected presets or selected folders
- `Save Group`: save multiple layers as one grouped preset

### Utilities

- `Transfer Presets`: open import/export actions
- `Shortcuts`: edit keyboard shortcuts
- `Appearance`: open panel appearance settings
- `Inspect Preset`: inspect the selected preset in a readable report
- `Random Preset`: randomly choose and apply a preset
- `Thumb`: attach, update, clear, or capture a preview thumbnail for compatible color-tagged presets
- `Preview`: open the larger preview viewer for a compatible preset when previews are enabled and a thumbnail exists

### Support

- `Contact`: open the built-in contact/support flow
- `Troubleshooting`: open logs and diagnostic tools

## Installation

### Quick Run

1. Open Adobe After Effects.
2. Go to `File > Scripts > Run Script File...`
3. Select the script file.

### Dockable Panel Install

1. Copy the script into the After Effects `Scripts/ScriptUI Panels` folder.
2. Keep the `ui-icons` folder beside the script.
3. Restart After Effects.
4. Open the panel from the `Window` menu.

Typical macOS panel path:

```text
/Applications/Adobe After Effects <version>/Scripts/ScriptUI Panels/
```

## Packaging Note

If you share this publicly, do not send only the script file by itself.

Keep these together in the same release folder:

- the script file
- the `ui-icons` folder

This build uses icon assets from `ui-icons` for parts of the preset list UI.

## File Storage

The script stores working files in the user data area under `LayerVaultPro`.

Typical macOS locations:

```text
~/Library/Application Support/LayerVaultPro/presets
~/Library/Application Support/LayerVaultPro/settings.json
~/Library/Application Support/LayerVaultPro/recovery-log.txt
~/Library/Application Support/LayerVaultPro/thumbnails
```

These are user-local paths, so sharing the script does not hardcode your own machine paths into another user's install.

## Basic Use

### Save A Preset

1. Open a comp.
2. Select one or more layers.
3. Click `Save Preset`.
4. Enter a name.

### Save A Group

1. Open a comp.
2. Select at least two layers.
3. Click `Save Group`.
4. Enter a group name.

### Apply A Preset

1. Open the destination comp.
2. Select a preset in the library.
3. Click `Apply Preset`.
