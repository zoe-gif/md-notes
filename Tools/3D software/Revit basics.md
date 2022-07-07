---
title: Revit Basics
date: 2022-07-05
update: 2022-07-05
categories:
- Tools
- 3D
tags: Revit
description: 
---

### Basics

- Element hierachy
    - Model elements
        - Category >> Family >> Type >> Object
    - Annotation elements
    - View elements
- Select
    - `shift + select` to deselect
    - `tab` to switch selection
    - Ribbon - Filter to select current categories
    - Select toggel - Select under Modify or right bottom
        - Links
        - Underlay elements
        - Pinned elements
- Project Browser
    - Double click view elements to go there, level too
    - Right click parent view to search
- Navigation
    - `ZR`: zoom in region
    - `ZF`: zoom to fit
    - `ZO`: zoom out 2x
    - `ZS`: zoom to sheet size (to scale)
    - `WT`: View - Tile view
    - `ZA`: zoom all to fit for multiple windows
- Options
    - General - View options - Architectural
    - User interface - Customize double-click setting - Family - Do nothing
    - File location
- Temporary dimension - two dimensions either side, can change references
- `space` to rotate elements 90 degrees
- Bottom contorl bar
    - 

### Draw, Modify and Geometry

- Draw
    - When drawing, also use modify command under ribbon
    - Line
    - Rectangle
    - Indescribed polygon: polygon inside circle
    - Circumscribed polygon: polygon outside circle
    - Circle
    - Star-end-radius arc
    - Circle-ends arc
    - Tangent end arc: create based on existing ends
    - Fillet arc: select existing lines to fillet
    - Ellipse
    - Partial ellipse
    - Pick lines
- Modify
    - Aligh `AL`
    - Move `MV`
    - Offset `OF`
    - Copy `CO`
    - Rotate `RO`
    - Trim and extend `TR`
        - Click parts to keep
    - Mirror pick axis `MM`
    - Mirror draw axis `DM`
    - Split `SL`
    - Array `AR`
    - Scale `RE`
    - Delete `DE`
- Geometry
    - Notch: add notch for steel beam and column
    - Cut/uncut geometry
    - Join/unjoin geometry, switch join order
    - Split face
        - Divid finish of element to apply different materials
        - Still in one element
    - Beam/Column joins
    - Paint: apply material to the face of an element
    - Wall joins
    - Demolish
        - Mark elements as demolished in current phase

### General workflow

- Project setup
    - Create from template
    - Manage - project info; project unit; location
- Add level `LL`
    - Checkbox to display or not level annotation
    - Pickline + offset
- Add grid `GR`
    - Grid acts like a plane, shown on layout and elevation
- Add column `CL`
    - Architectural or structural
    - Constraints
        - Move with grids
    - Architectural column can merge into other building elements
    - Structural column
        - Multiple - at grids/architectural columns
- Add wall `WA`
    - Constraints to set height
    - 