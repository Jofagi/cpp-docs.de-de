---
title: ODBC-Klassen und Threads
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: 1d470e79ba5a6a73a30743a21da0462a6b89e7da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608168"
---
# <a name="odbc-classes-and-threads"></a>ODBC-Klassen und Threads

Ab MFC 4.2 ist Multithreadingunterstützung für die MFC-ODBC-Klassen. Beachten Sie jedoch, dass MFC keine Unterstützung von multithreading für den DAO-Klassen bereitstellt.

Die Multithreadingunterstützung für die ODBC-Klassen gelten einige Einschränkungen. Da diese Klassen, die ODBC-API umschließen, sind sie auf die Unterstützung von multithreading der Komponenten auf denen sie erstellt werden beschränkt. Viele ODBC-Treiber sind beispielsweise nicht threadsicher. aus diesem Grund sind die MFC-ODBC-Klassen nicht threadsicher, wenn Sie mit einem dieser Treiber verwendet werden. Sie sollten überprüfen, ob Ihre bestimmte Treiber threadsicher ist.

Wenn Sie eine Multithreadanwendung erstellen zu können, sollten Sie sehr sorgfältig bei der Verwendung von mehreren Threads auf dasselbe Objekt bearbeiten können. Verwenden Sie beispielsweise die gleiche `CRecordset` Objekt in zwei Threads verursachen möglicherweise Probleme beim Abrufen von Daten; ein Fetch-Vorgang in einem Thread möglicherweise die Daten abgerufen werden, in dem anderen Thread zu überschreiben. Eine weitere häufige Verwendung für die MFC-ODBC-Klassen in separaten Threads ist ein offenes freigeben `CDatabase` -Objekt threadübergreifend verwenden die gleiche ODBC-Verbindung mit einem separaten `CRecordset` Objekt in jedem Thread. Beachten Sie, dass Sie kein ungeöffnetes übergeben, sollten `CDatabase` -Objekt an eine `CRecordset` Objekt in einem anderen Thread.

> [!NOTE]
>  Wenn Sie mehrere Threads, die das gleiche Objekt bearbeitet haben müssen, sollten Sie die entsprechenden Synchronisierungsmechanismen, z. B. kritische Abschnitte implementieren. Beachten Sie, dass bestimmte Vorgänge, z. B. `Open`, sind nicht geschützt. Sie sollten sicher sein, dass diese Vorgänge nicht gleichzeitig in separaten Threads aufgerufen werden.

Weitere Informationen zum Erstellen von Multithread-Anwendungen finden Sie unter [Themen zu Multithreading](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Datenzugriffsprogrammierung (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)