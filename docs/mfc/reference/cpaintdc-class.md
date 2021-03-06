---
title: CPaintDC-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: 991ea39ccf03cd4f2921a759d3278576c7a1fd92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525748"
---
# <a name="cpaintdc-class"></a>CPaintDC-Klasse

Eine Gerätekontext abgeleitete Klasse [CDC](../../mfc/reference/cdc-class.md).

## <a name="syntax"></a>Syntax

```
class CPaintDC : public CDC
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Erstellt eine `CPaintDC` verbunden mit dem angegebenen [CWnd](../../mfc/reference/cwnd-class.md).|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|Enthält die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) verwendet, um den Clientbereich zu zeichnen.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|Das HWND zu der das `CPaintDC` Objekt angefügt ist.|

## <a name="remarks"></a>Hinweise

Er führt eine [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) zur Erstellungszeit und [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) zur zerstörungszeit.

Ein `CPaintDC` Objekt kann nur verwendet werden, für die Reaktion auf eine [WM_PAINT](/windows/desktop/gdi/wm-paint) Nachricht werden in der Regel Ihre `OnPaint` -Nachrichtenhandler-Memberfunktion.

Weitere Informationen zur Verwendung von `CPaintDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC

Erstellt eine `CPaintDC` -Objekt, das Anwendungsfenster für zeichnen vorbereitet und speichert die [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) Struktur der [M_ps](#m_ps) Membervariablen gespeichert.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
Verweist auf die `CWnd` -Objekt, dem die `CPaintDC` Objekt gehört.

### <a name="remarks"></a>Hinweise

Eine Ausnahme (vom Typ `CResourceException`) wird ausgelöst, wenn die Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) -Aufruf fehl. Ein Gerätekontext möglicherweise nicht verfügbar, wenn es sich bei allen Kontexten verfügbare Gerät Windows bereits zugewiesen wurde. Ihre Anwendung Computerressourcen für die fünf allgemeinen Anzeige Kontexte zu jedem Zeitpunkt unter Windows verfügbar.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd

Die `HWND` zu der das `CPaintDC` Objekt angefügt ist.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Hinweise

*M_hWnd* ist eine geschützte Variable des Typs HWND.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>  CPaintDC::m_ps

`m_ps` ist eine öffentlicher Member-Variable des Typs [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Hinweise

Es ist die `PAINTSTRUCT` , übergeben und ausgefüllt von [CWnd:: BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).

Die `PAINTSTRUCT` enthält Informationen, die die Anwendung verwendet wird, um den Clientbereich des zugeordneten Fensters zeichnen eine `CPaintDC` Objekt.

Beachten Sie, dass Sie, das Gerätekontext Handle durch zugreifen können die `PAINTSTRUCT`. Es stehen jedoch das Handle, der direkt über die `m_hDC` Membervariable, `CPaintDC` erbt von der CDC.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CPaintDC::m_hWnd](#m_hwnd).

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../visual-cpp-samples.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

