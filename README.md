# VRMLiveViewer-AutoCamera

Unofficial documentation and samples for creating and adjusting camera work for VRM Live Viewer's Manual Camera Settings (Auto Camera Settings) with generative AI such as ChatGPT or Gemini.

**[日本語 README](README_JA.md)**

## Getting Started

Give the specification and sample JSON to a generative AI, then describe the BPM, frame range, character number, and the camera work you want in natural language. The AI can use these materials to create AutoCamera JSON for VRM Live Viewer.

## Files

- [Getting Started Guide](docs/Getting_Started_EN.md) - Step-by-step workflow for creating Manual Camera Settings with generative AI
- [AutoCamera JSON Specification (English)](docs/AutoCamera_JSON_Spec_EN.pdf) - AutoCamera JSON settings, UI mappings, and rules for combining camera parts
- [AutoCamera Sample JSON](samples/full_camera_sample_6660f_160bpm.json) - Example output of generated camera work

The sample JSON is not a preset for a specific song. It is an example AutoCamera output combining horizontal orbits, rolls, Dutch angles, sideways compositions, zooms, dolly movements, Jitter, and other effects. Its frame placement assumes 6660 frames and 160 BPM as an example.

## Important Notes

- This is an unofficial project and is not an official project of the developer of VRM Live Viewer.
- When publishing videos made with these materials on YouTube or other services, check the terms of use and rights for the music, models, motions, choreography, stages, costumes, and any other materials you use.
- When using distributed motions or choreography, check the credit requirements and usage conditions specified by the distributor, creator, performer/dancer, or other relevant rights holder, and include any required acknowledgements or credits.
- Please do not send questions about this project to the developer of VRM Live Viewer. The developer of VRM Live Viewer does not provide support for this project.

## Terminology

- **Camera work**: the overall camera movement, composition, and visual direction
- **Frame**: a position on the timeline
- **Camera data**: one element of `datas[]` in an AutoCamera JSON file
- **Camera part**: a reusable camera setting made of one or more camera-data entries

## Getting Started

After reviewing the notes above, follow the guide below to create your AutoCamera JSON.

### ▶ [Getting Started with Manual Camera Settings Using Generative AI](docs/Getting_Started_EN.md)

## License

Documents and sample data independently created by MoonaWorks in this repository are provided under [CC0 1.0 Universal](LICENSE). No attribution is required.

This does not apply to VRM Live Viewer itself, the VRM Live Viewer name or logo, or music, models, motions, choreography, stages, costumes, or other materials created by third parties.

Document Version: 1.1
Updated: 2026-09-09

Revision History
v1.1
- Revised the 360-degree rotation method based on actual testing
- Added verified one-way/back-and-forth behavior of rotationHalf
- Added the verified relationship between rotationTime, fps, and frame-based timing
- Added verified information about farClip (clip distance)
