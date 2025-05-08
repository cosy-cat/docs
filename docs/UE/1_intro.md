---
title: Intro
tags:
- unreal-engine
---

# Tips

**BeginPlay**:

- play/F8 == disembody to see the pawn
- F8 again to possess again
- auto action by UE : on play a pawn is created from start location : in BP, `get pawn...`

**BluePrint**:

- create BluePrint from actor : right panel icon (3 squares)

**BluePrint Canvas**:

- get pawn
- get forward vector
- spawn from (BP, ...)
- select multiple and right clic to make a  function of a bloc

**BluePrint Level**

- select object (cube, etc..) from the main scene
- clic open Level Blue Print
- right clic "create a reference to the _object_"

> make a reusable blueprint such a bullet, but/and instantiate it from the level blueprint

**BSP (Binary Space Partitioning)**:

- fast level prototyping
- ⚙️  How to Use BSP in Unreal Engine:

      Open the Selection Mode Panel from the drop down under level name.
      Select BSP (Geometry) and choose a shape (Box, Cylinder, etc.).
      Drag the shape into the level.
      Modify its size and shape in the Details Panel.
      Convert to Static Mesh when the design is finalized (Right-click → Convert to Static Mesh).

- 📌 Types of BSP Brushes:

      Additive Brush: Creates solid geometry.
      Subtractive Brush: Cuts away from existing geometry.

- ⚠️  Performance Considerations: BSP is not as optimized as static meshes and should generally be replaced with static meshes for the final level.

**GameModes**

Change game mode (from TPs to FPs) by:
- open content drawer, clic + add button, add feature/content pack, 1st or 3rd Person BP
- open Project Settings, Project Maps and Modes, change default Pawn Class to desired BP
