---
title: CSplitterWndEx-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: fa58dbffc3e6416c18b8124f8e5edfe1ce987815
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538995"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx-Klasse

Stellt ein benutzerdefiniertes unterteiltes Fenster dar.

## <a name="syntax"></a>Syntax

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Standardkonstruktor|
|`CSplitterWndEx::~CSplitterWndEx`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Wird aufgerufen, durch das Framework zum Zeichnen eines unterteilten Fensters. (Überschreibt [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Hinweise

Überschreiben der `OnDrawSplitter` Methode, um die Darstellung der grafischen Komponenten eines unterteilten Fensters anpassen.

Die `CSplitterWndEx` -Klasse dient zusammen mit den [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), und [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) -Methoden, die sind durch einen visuellen Manager implementiert. Um einen visuellen Manager zum Zeichnen ein Teilungsfenster in Ihrer Anwendung zu verursachen, ersetzen Sie die Deklarationen der `CSplitterWnd` -Klasse mit der `CSplitterWndEx` Klasse. Für Anwendungen der Frame-Fenster ist die Fensterklasse des Splitters in der CMainFrame-Klasse deklariert, die in "MainFrm.h" befindet. Ein Beispiel finden Sie unter den `OutlookDemo` Beispiel im Verzeichnis "Samples".

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxsplitterwndex.h

##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter

Wird aufgerufen, durch das Framework zum Zeichnen eines unterteilten Fensters.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf den Gerätekontext. Wenn dieser Parameter NULL ist, zeichnet das Framework des aktiven Fensters.

*nType*<br/>
[in] Eines der `CSplitterWnd::ESplitType` Enumerationswerte, der angibt, das Splitter-Fenster-Element zu zeichnen. Gültige Werte sind `splitBox`, `splitBar`, `splitIntersection` und `splitBorder`.

*Rect*<br/>
[in] Ein umgebendes Rechteck, das die Abmessungen und Position Zeichnen des Elements der angegebenen Splitter Fenster angibt.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../hierarchy-chart.md)<br/>
[Klassen](mfc-classes.md)<br/>
[CSplitterWnd-Klasse](csplitterwnd-class.md)<br/>
[CMFCVisualManager-Klasse](cmfcvisualmanager-class.md)