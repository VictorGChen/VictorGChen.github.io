---
layout: page
title: Unity Game Project 1
description: Interactive Unity WebGL game - Coming Soon
img:
importance: 3
category: featured
---

## Coming Soon

This page will feature an embedded Unity WebGL game built with Unity Engine.

### Planned Features

- Interactive gameplay directly in the browser
- WebGL-based rendering for cross-platform compatibility
- Engaging mechanics and polished user experience

### Technical Stack

- **Engine**: Unity
- **Platform**: WebGL
- **Languages**: C#, JavaScript

---

## How to Embed Unity WebGL Games

When ready to add the game, the Unity WebGL build will be embedded using:

```html
<div class="unity-container">
  <canvas id="unity-canvas"></canvas>
  <script src="Build/UnityLoader.js"></script>
  <script>
    UnityLoader.instantiate("unity-canvas", "Build/game.json");
  </script>
</div>
```

### Steps to Add Your Game

1. Build your Unity project for WebGL
2. Upload the Build folder to `assets/unity/game1/`
3. Update this page with the embed code
4. Add a thumbnail image to the `img:` field in the front matter

---

**Status**: In Development

Check back soon for the playable version!
