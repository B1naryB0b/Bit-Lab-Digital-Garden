# Video Support in Bit Lab Digital Garden

Video support has been added to your digital garden. You can now embed videos in your markdown files using either Obsidian-style embed syntax or code block syntax.

## Obsidian-Compatible Usage (Recommended)

The easiest way to embed videos, which works directly in Obsidian:

```markdown
![[video.mp4]]
```

Just like images, you can also specify a width:

```markdown
![[video.mp4|600]]
```

This syntax works exactly like Obsidian's image embeds, but automatically detects video files and creates a video player instead.

## Code Block Syntax (Advanced)

For more control over video playback, use the code block syntax:

````markdown
```video
src: /videos/your-video.mp4
controls: true
width: 100%
```
````

## Options

The video code block supports the following options:

- `src`: (Required) Path to your video file. Place your videos in `src/site/videos/` and reference them as `/videos/filename.mp4`
- `controls`: Show video controls (default: true)
- `autoplay`: Auto-play the video (default: false)
- `loop`: Loop the video (default: false)
- `muted`: Mute the video (default: false)
- `width`: Set the video width (default: 100%)
- `poster`: Set a poster image (thumbnail) for the video

## Examples

### Basic Video
````markdown
```video
src: /videos/demo.mp4
```
````

### Video with Custom Settings
````markdown
```video
src: /videos/tutorial.mp4
controls: true
width: 80%
poster: /img/thumbnail.jpg
```
````

### Looping Background Video
````markdown
```video
src: /videos/background.mp4
autoplay: true
loop: true
muted: true
controls: false
```
````

## Supported Video Formats

The video player supports common web video formats:
- MP4 (recommended)
- WebM
- OGG

For best compatibility across browsers, use MP4 format.

## File Organization with Digital Garden Plugin

### How the Plugin Handles Videos (Automatic)

When you use the **Digital Garden Obsidian plugin** to publish notes:

1. **In Obsidian**: Store videos anywhere in your vault (just like images)
2. **Embed them**: Use `![[video.mp4]]` in your notes
3. **Hit Publish**: The plugin automatically:
   - Copies videos to `src/site/img/user/` in this repository
   - Updates references to work on the web
   - Creates video players on the published site

**This works exactly like images - no special setup needed!** The plugin treats videos the same way it treats images.

### Manual Video Organization (Optional)

If you're adding videos directly to the repository (not through Obsidian):

1. Place videos in: `src/site/videos/` or `src/site/img/user/`
2. Reference as: `![[/videos/video.mp4]]` or `![[/img/user/video.mp4]]`

Both locations work because they're included in the build passthrough configuration.

## Styling

Videos are automatically styled to match your digital garden theme with:
- Responsive width (max 100%)
- Rounded corners (15px border radius)
- Proper spacing (1em margin)
- Theme-aware background color

The styling can be customized in `src/site/styles/custom-style.scss` under the `.video-container` class.