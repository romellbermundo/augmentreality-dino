# 🦖 T-REX ENCOUNTER

<div align="center">

**THE PREHISTORIC WORLD. IN YOUR WORLD.**

*Sixty-six million years apart. One extraordinary encounter.*

*Bring a giant dinosaur out of the screen and into your surroundings.*

[🌐 Live Website](https://augmentreality-dino.pages.dev/) · [📦 Source Code](https://github.com/romellbermundo/augmentreality-dino)

</div>

> **Compatibility note:** The website is published on Cloudflare Pages. AR requires HTTPS, a compatible device and browser, and permission to use augmented reality. The original T-Rexaur game model is a prototype asset, not a scientifically accurate Tyrannosaurus rex.

---

## 📑 Table of Contents

- [About T-Rex Encounter](#-about-t-rex-encounter)
- [How It Works](#-how-it-works)
- [Key Features](#-key-features)
- [Getting Started](#-getting-started)
- [Publishing the Website](#-publishing-the-website)
- [Project Structure](#-project-structure)
- [Technology](#-technology)
- [Design Philosophy](#-design-philosophy)
- [Privacy and Limitations](#-privacy-and-limitations)
- [Credits](#-credits)
- [Version History](#-version-history)

---

## 📖 About T-Rex Encounter

**Imagine looking across your own room, driveway, or backyard—and seeing a towering dinosaur standing there.**

**T-Rex Encounter** is an experimental, mobile-first augmented reality project designed to turn that idea into an interactive experience. On a compatible Android phone, the app can detect a real-world surface and place a 3D dinosaur at the chosen location. On other devices, visitors can still explore the dinosaur in an interactive 3D scene.

The project began as an A-Frame playground filled with assorted models, objects, and experiments. It has since been rebuilt around one clear idea: **one dinosaur, one encounter, and the feeling that the prehistoric world has entered our own.**

The current dinosaur is the original T-Rexaur asset already present in the repository. It provides a useful technical prototype, but a properly licensed realistic T-Rex model would be a future improvement.

---

## 🔄 How It Works

```text
       OPEN T-REX ENCOUNTER
                 │
                 ▼
         EXPLORE IN 3D
          rotate / zoom
                 │
                 ▼
       CHOOSE START AR
                 │
       ┌─────────┴─────────┐
       ▼                   ▼
  AR SUPPORTED        AR UNAVAILABLE
       │                   │
       ▼                   ▼
 SCAN THE GROUND      KEEP EXPLORING
       │                 IN 3D
       ▼
 TAP TO PLACE
       │
       ▼
   MEET YOUR T-REX
       │
       ▼
 MINI ↔ GIANT / LEFT ↔ RIGHT / RESET
```

The 3D viewer uses Three.js. On supported Android devices, WebXR hit testing identifies surfaces so the dinosaur can be placed in the camera view. Unsupported browsers continue to use the standard 3D viewer.

---

## ✨ Key Features

### 🦖 A Dinosaur Encounter

View the existing textured dinosaur model in a dedicated scene rather than an assortment of unrelated test objects.

### 📱 Augmented Reality Placement

On compatible Android phones, enter WebXR AR, scan a horizontal surface, and use the Place T-Rex button to position the dinosaur in the real world.

### 🔍 Interactive 3D Viewer

Drag to orbit around the dinosaur and pinch or scroll to zoom. Explore without enabling the camera.

### 📏 Life-sized and Miniature Modes

Switch between an approximately 4.1-metre-tall model and a smaller tabletop-scale version. The Mini/Giant switch animates smoothly. Size is approximate and intended for demonstration.

### 🔄 Left / Right Rotation and Reset

Use separate **↶ Left** and **Right ↷** buttons to turn the dinosaur 45° in either direction with a short, smooth transition. **Reset** dissolves the dinosaur and reopens the placement portal; in AR, place it again at a new location.

### ✨ Time-travel Portal

A glowing portal with animated particles marks the placement area. The dinosaur materializes through it, then the particles disappear and the portal shrinks away. Reset fades out the dinosaur and expands the portal again for another encounter. Once placed, the dinosaur cannot be moved without resetting.

### 🌿 Focused Interface

A dark forest-inspired palette, soft glass-like panels, and compact controls keep attention on the dinosaur rather than the interface.

### 🧭 Progressive Enhancement

The standard 3D viewer remains available when immersive AR is unsupported. AR is an additional capability, not a requirement for exploring the model.

---

## 🚀 Getting Started

### Option A — Run locally

Clone the repository:

```bash
git clone https://github.com/romellbermundo/augmentreality-dino.git
cd augmentreality-dino
python -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) for the 3D viewer.

For phone-based AR, publish the site over HTTPS; a computer's local HTTP address generally will not satisfy the secure-context requirement.

### Option B — Open the published website

Open the live site at **https://augmentreality-dino.pages.dev/** in a supported mobile browser. On compatible Android devices, choose **Start AR**, allow the required permissions, move your phone to detect the ground, and tap to place the dinosaur.

**Compatibility:** WebXR immersive AR and hit testing require a compatible Android device, browser, and AR services. iOS Safari does not support this implementation's WebXR AR workflow.

---

## 🌐 Publishing the Website

This is a static website. It does not require a production build step.

A suitable option is **Cloudflare Pages**:

1. Create a Cloudflare Pages project connected to this GitHub repository.
2. Choose a static-site deployment with no framework preset.
3. Leave the build command empty and set the output directory to the repository root, if requested.
4. Deploy and open the generated HTTPS address.
5. Test both the 3D viewer and AR on a compatible phone.

The project is published through Cloudflare Pages at **https://augmentreality-dino.pages.dev/**, with GitHub-connected deployments. Allow deployment to complete before testing recent changes.

---

## 🏗️ Project Structure

```text
augmentreality-dino/
├── index.html
├── assets/
│   └── psone/
│       ├── t-rexaur.obj
│       ├── t-rexaur.mtl
│       └── ffdtex*.png
├── package.json
└── README.md
```

The current interface and rendering logic live in `index.html`. The `assets/psone/` directory contains the legacy dinosaur model and its materials. The repository also retains older experimental assets that are no longer central to the new experience.

---

## 🛠️ Technology

| Layer | Technology |
|---|---|
| 3D rendering | Three.js |
| AR framework | WebXR immersive AR and hit testing |
| Model loading | Three.js OBJLoader and MTLLoader |
| Interface | HTML, CSS, JavaScript |
| Asset format | OBJ, MTL, PNG |
| Hosting | Cloudflare Pages (HTTPS) |
| Version control | Git and GitHub |

---

## 🎨 Design Philosophy

**A prehistoric encounter should feel extraordinary without being complicated.**

The interface is designed as a quiet frame around the dinosaur: deep forest tones, restrained highlights, tactile controls, and enough information to guide the visitor without overwhelming the screen.

- **Wonder before complexity:** A dinosaur in your own surroundings is the experience—not a crowded menu.
- **The real world as the stage:** In AR mode, the camera view becomes the environment.
- **Control without clutter:** Placement, size, rotation, and reset remain simple.
- **Accessible exploration:** A non-AR 3D viewer gives more visitors a way to interact.
- **A foundation for growth:** Better models, animations, sound, and improved tracking can be added without abandoning the central idea.

*One step out of the past. One step into your world.*

---

## 🔒 Privacy and Limitations

- **No account is required.** The experience does not include user registration or sign-in.
- **Camera access in AR:** Compatible AR sessions require camera-related device permissions. The application does not intentionally upload or store camera footage.
- **External dependencies:** Three.js modules load from a third-party CDN; normal network requests are made to retrieve these scripts.
- **Device compatibility:** AR surface placement is not universally supported, particularly on iOS Safari.
- **Experimental tracking:** Surface detection, positioning, lighting, and performance vary by device and environment.
- **Model accuracy:** The current T-Rexaur game asset is not a scientifically accurate Tyrannosaurus rex.
- **Asset licensing:** Confirm redistribution rights for the legacy model and textures before making the project public.
- **Safety:** Stay aware of physical obstacles and other people while using the camera-based experience.

---

## 🙏 Credits

**Original experiment and portfolio project:** Romell Bermundo.

**Original project technology:** A-Frame, JavaScript, and assorted experimental 3D assets.

**Current implementation:** Three.js and WebXR, using the original T-Rexaur model retained from the repository.

**Third-party model and texture attribution:** The original creator and license have not yet been verified. Attribution and redistribution permission should be established before public release.

---

## 🏷️ Version History

### v2.1.0 — Portal animations and dual rotation

- Added separate smooth left/right 45° rotation controls and animated Mini/Giant scaling.
- Added the glowing particle portal, dinosaur arrival animation, automatic portal closing, and animated Reset sequence.
- Improved AR floor placement and retained fallback positioning when tracking is unavailable.
- Updated documentation with the live Cloudflare Pages link and current interactions.

### v2.0.1 — Portfolio documentation

- Rebuilt the README using the structured, editorial documentation style of the NEXUS 01 calculator.
- Added the project story, interaction diagram, feature explanations, publishing guidance, technical architecture, design philosophy, limitations, credits, and version history.
- Clarified that deployment and phone-based AR compatibility still need verification.

### v2.0.0 — T-Rex Encounter

- Replaced the old experimental A-Frame scene with a dedicated Three.js dinosaur viewer.
- Added WebXR hit-test-based AR placement for compatible Android devices.
- Added miniature and approximately life-sized viewing modes, rotation, and reset.
- Retained the original T-Rexaur model and textures.

### v1.0.0 — Augmented Reality Test Repository

- Created an A-Frame-based 3D experimentation environment with assorted models, materials, shapes, and interactive objects.
- Established the repository as a learning space for web-based 3D and augmented reality experiments.
