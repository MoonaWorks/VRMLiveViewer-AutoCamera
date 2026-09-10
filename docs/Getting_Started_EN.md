# Getting Started with VRMLiveViewer Manual Camera Settings Using Generative AI

## Creating and Adjusting AutoCamera JSON with Generative AI

This guide explains how to create JSON files for VRM Live Viewer's Manual Camera Settings (Auto Camera Settings) using generative AI such as ChatGPT or Gemini.

This is an unofficial project and is not official documentation from the developer of VRM Live Viewer.

## 1. What You Need

- VRM Live Viewer
- A generative AI service that can read attached files, such as ChatGPT or Gemini
- [AutoCamera JSON Specification (English)](AutoCamera_JSON_Spec_EN.pdf)
- [AutoCamera Sample JSON](../samples/full_camera_sample_6660f_160bpm_v1.1.json)

## 2. Basic Workflow

| Step | What to Do |
|---|---|
| 1 | Prepare the character, motion, music, and other materials you will use in VRM Live Viewer. |
| 2 | Check the start frame, end frame, BPM, character number, and other conditions for the range where you want to create camera work. |
| 3 | Attach the AutoCamera JSON Specification and the sample JSON to the generative AI. |
| 4 | Describe the camera work you want in natural language. |
| 5 | Save the generated AutoCamera JSON as a `.json` file. |
| 6 | Drag and drop the saved AutoCamera JSON into VRM Live Viewer. |
| 7 | Play the scene and check the camera work. |
| 8 | If necessary, manually adjust the camera settings at the frames that need correction. For major changes, tell the generative AI what to change and regenerate the JSON. |
| 9 | If you do not know which parameter to change during manual adjustment, ask the same chat that generated the JSON for candidate parameters to modify. |

## 3. Files to Give the Generative AI

At minimum, provide the following two files to the generative AI in the same conversation:

- [AutoCamera JSON Specification (English)](AutoCamera_JSON_Spec_EN.pdf)
- [AutoCamera Sample JSON](../samples/full_camera_sample_6660f_160bpm.json)

The sample JSON is an example AutoCamera output, not a preset for a specific song.

It is provided as a reference for combining horizontal orbits, rolls, Dutch angles, sideways compositions, zooms, dolly movements, Jitter, and other camera effects.

The sample assumes a total length of 6660 frames and 160 BPM, with camera changes placed roughly by musical measure.

## 4. Writing the Prompt

You do not need to provide the song title. Check the BPM and total frame count in advance.

The AI needs the conditions for placing the camera data and the camera effects you want.

Keep the following sentence at the end of the prompt:

> Output an AutoCamera JSON file that VRM Live Viewer can read, as a single-line minified JSON.

Do not remove this sentence.

### Example

> Total length: 6660 frames, 160 BPM, starting at frame 0.  
> Keep Character 1 fixed.  
> Create highly active camera work.  
> Include a horizontal 360-degree orbit, a 360-degree screen roll, a 45-degree Dutch angle,  
> a 90-degree sideways composition, zoom in/out, dolly movement, and Jitter.  
> You may choose the timing for now.  
>
> Output an AutoCamera JSON file that VRM Live Viewer can read, as a single-line minified JSON.

## 5. Using the Generated JSON

Save the JSON received from the generative AI as a `.json` file, then drag and drop it into VRM Live Viewer.

## 6. Fine-Tuning After Playback

You can ask the generative AI which setting to change without regenerating the entire JSON.

Giving the frame number and describing the problem makes the request clearer.

| Example Request | Main Adjustment Candidate |
|---|---|
| The 45-degree tilt at frame 1800 is too strong | Rotation Z / `angle` Z |
| Make the zoom-in a little weaker | Distance / Add Distance / `distanceMax` |
| Make the rotation a little slower | Changing Rotation → Changing Time / `rotationTime` |
| The shake is too strong | Jitter → Position Amount / Rotation Amount |
| Reduce the horizontal movement by about half | Changing Position → Add X / `positionMax` X |

## 7. 360-Degree Rotation

A 360-degree rotation can be specified with a single camera-data entry.

For a one-way 360-degree rotation, use `rotationHalf=True` (One Way).

When `rotationHalf=False`, the rotation moves back and forth: after reaching the maximum angle, it reverses and returns toward the starting angle.

## 8. Troubleshooting

- **The JSON does not load**  
  Check that the final JSON is a single-line minified file.

- **The camera work is not what you intended**  
  Tell the AI the frame number and what is different.

- **You do not understand a setting**  
  Refer to the UI-name / JSON-key mapping table in the specification.

## 9. Detailed Specification

For individual settings, UI mappings, and rules for combining multiple camera parts, see the [AutoCamera JSON Specification (English)](AutoCamera_JSON_Spec_EN.pdf).

## 10. Notes for Publishing Videos

- This is an unofficial project and is not an official project of the developer of VRM Live Viewer.
- When publishing videos made with these materials on YouTube or other services, check the terms of use and rights for the music, models, motions, choreography, stages, costumes, and any other materials you use.
- When using distributed motions or choreography, check the credit requirements and usage conditions specified by the distributor, creator, performer/dancer, or other relevant rights holder, and include any required acknowledgements or credits.
- Please do not send questions about this project to the developer of VRM Live Viewer. The developer of VRM Live Viewer does not provide support for this project.
