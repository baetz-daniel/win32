---
Description: 'In addition to the update region, every window has a visible region that defines the window portion visible to the user.'
ms.assetid: '9d8beba1-93c0-437d-a138-76880a40bc79'
title: Window Regions
---

# Window Regions

In addition to the update region, every window has a *visible region* that defines the window portion visible to the user. The system changes the visible region for the window whenever the window changes size or whenever another window is moved such that it obscures or exposes a portion of the window. Applications cannot change the visible region directly, but the system automatically uses the visible region to create the clipping region for any display device context retrieved for the window.

The *clipping region* determines where the system permits drawing. When the application retrieves a display device context using the [**BeginPaint**](beginpaint.md), [**GetDC**](getdc.md), or [**GetDCEx**](getdcex.md) function, the system sets the clipping region for the device context to the intersection of the visible region and the update region. Applications can change the clipping region by using functions such as [**SetWindowRgn**](setwindowrgn.md), [**SelectClipPath**](selectclippath.md) and [**SelectClipRgn**](selectcliprgn.md), to further limit drawing to a particular portion of the update area.

The WS\_CLIPCHILDREN and WS\_CLIPSIBLINGS styles further specify how the system calculates the visible region for a window. If a window has one or both of these styles, the visible region excludes any child window or sibling windows (windows having the same parent window). Therefore, drawing that would otherwise intrude in these windows will always be clipped.

 

 


