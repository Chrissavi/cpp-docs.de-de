---
title: 'WM_-Meldungen: P - R'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_RBUTTONUP
- ON_WM_PALETTECHANGED
- ON_WM_RBUTTONDBLCLK
- ON_WM_QUERYENDSESSION
- ON_WM_PARENTNOTIFY
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYOPEN
- ON_WM_PAINT
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONDOWN
- ON_WM_RENDERALLFORMATS
- ON_WM_PAINTCLIPBOARD
- ON_WM_RENDERFORMAT
- ON_WM_QUERYDRAGICON
helpviewer_keywords:
- ON_WM_RENDERFORMAT [MFC]
- ON_WM_QUERYOPEN [MFC]
- ON_WM_RBUTTONDOWN [MFC]
- ON_WM_PAINTCLIPBOARD [MFC]
- ON_WM_QUERYNEWPALETTE [MFC]
- ON_WM_RBUTTONUP [MFC]
- ON_WM_PARENTNOTIFY [MFC]
- ON_WM_RBUTTONDBLCLK [MFC]
- ON_WM_PALETTECHANGED [MFC]
- ON_WM_PALETTEISCHANGING [MFC]
- ON_WM_QUERYDRAGICON [MFC]
- ON_WM_PAINT [MFC]
- ON_WM_RENDERALLFORMATS [MFC]
- ON_WM_QUERYENDSESSION [MFC]
- WM_ messages
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
ms.openlocfilehash: ff34f8d25a48cffd75bed6b13c5811a6cabd9c53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636617"
---
# <a name="wm-messages-p---r"></a>WM_-Meldungen: P - R

Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen:

|Zuordnungseintrag|Funktionsprototyp|
|---------------|------------------------|
|ON_WM_PAINT()|die "void" Afx_msg [OnPaint](../../mfc/reference/cwnd-class.md#onpaint)();|
|ON_WM_PAINTCLIPBOARD()|die "void" Afx_msg [OnPaintClipboard](../../mfc/reference/cwnd-class.md#onpaintclipboard)(CWnd *, HANDLE);|
|ON_WM_PALETTECHANGED()|die "void" Afx_msg [OnPaletteChanged](../../mfc/reference/cwnd-class.md#onpalettechanged)(CWnd *);|
|ON_WM_PALETTEISCHANGING()|die "void" Afx_msg [OnPaletteIsChanging](../../mfc/reference/cwnd-class.md#onpaletteischanging)(CWnd *);|
|ON_WM_PARENTNOTIFY()|die "void" Afx_msg [OnParentNotify](../../mfc/reference/cwnd-class.md#onparentnotify)(UINT, LONG);|
|ON_WM_POWERBROADCAST()|Afx_msg UINT [OnPowerBroadcast](../../mfc/reference/cwnd-class.md#onpowerbroadcast)("uint", "uint");|
|ON_WM_QUERYDRAGICON()|Afx_msg HCURSOR [OnQueryDragIcon](../../mfc/reference/cwnd-class.md#onquerydragicon)() (-).|
|ON_WM_QUERYENDSESSION()|Afx_msg "bool" [OnQueryEndSession](../../mfc/reference/cwnd-class.md#onqueryendsession)() (-).|
|ON_WM_QUERYNEWPALETTE()|Afx_msg "bool" [OnQueryNewPalette](../../mfc/reference/cwnd-class.md#onquerynewpalette)() (-).|
|ON_WM_QUERYOPEN()|Afx_msg "bool" [OnQueryOpen](../../mfc/reference/cwnd-class.md#onqueryopen)() (-).|
|ON_WM_RBUTTONDBLCLK()|die "void" Afx_msg [OnRButtonDblClk](../../mfc/reference/cwnd-class.md#onrbuttondblclk)(UINT, CPoint);|
|ON_WM_RBUTTONDOWN()|die "void" Afx_msg [OnRButtonDown](../../mfc/reference/cwnd-class.md#onrbuttondown)(UINT, CPoint);|
|ON_WM_RBUTTONUP()|die "void" Afx_msg [OnRButtonUp](../../mfc/reference/cwnd-class.md#onrbuttonup)(UINT, CPoint);|
|ON_WM_RENDERALLFORMATS()|die "void" Afx_msg [OnRenderAllFormats](../../mfc/reference/cwnd-class.md#onrenderallformats)();|
|ON_WM_RENDERFORMAT()|die "void" Afx_msg [OnRenderFormat](../../mfc/reference/cwnd-class.md#onrenderformat)(UINT);|

## <a name="see-also"></a>Siehe auch

[Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)<br/>
[Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

