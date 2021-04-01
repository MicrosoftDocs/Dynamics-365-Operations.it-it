---
title: Modelli di assistenza
description: È possibile definire un contratto di assistenza come modello e copiare in seguito le righe del modello in un altro contratto di assistenza o in un ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ade35eee21585aed2f542f4c977788aa3fe8804b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256137"
---
# <a name="service-templates"></a>Modelli di assistenza

[!include [banner](../includes/banner.md)]

È possibile definire un contratto di assistenza come modello e copiare in seguito le righe del modello in un altro contratto di assistenza o in un ordine di assistenza.

## <a name="example"></a>Esempio

Un cliente al quale si fornisce assistenza dispone di montacarichi identici presso cinque sedi diverse.

Per il cliente si desidera impostare cinque contratti di assistenza, uno per ciascuna sede.
Per limitare le operazioni ripetitive dell'attività di impostazione e per assicurarsi che le informazioni contenute nei contratti di assistenza siano identiche, è possibile creare un contratto di assistenza e specificarlo come modello delle attività di assistenza relative ai montacarichi.

È ora possibile copiare le righe del modello nei cinque nuovi contratti di assistenza.

## <a name="create-a-template"></a>Crea un modello

Per creare un modello di assistenza, creare un contratto di assistenza, creare le righe desiderate all'interno di esso, quindi collegare il contratto a un gruppo di modelli di assistenza.

> [!NOTE]
> È possibile definire un contratto di assistenza come modello solo se ad esso non è collegato alcun ordine di assistenza. Non è inoltre possibile generare ordini di assistenza da contratti di assistenza definiti come modelli.

## <a name="copy-template-lines"></a>Copia righe modello

È possibile copiare le righe di un modello di assistenza in un altro contratto di assistenza o in un ordine di assistenza.

Quando si copiano le righe del modello in un ordine o in un contratto di assistenza, i gruppi di modelli compaiono in una visualizzazione struttura in cui è possibile espandere ciascun gruppo. Questo tipo di visualizzazione consente di vedere ogni modello e ogni riga del modello.

Per determinare in modo più semplice le righe del modello da copiare, raggruppare i modelli assegnando ai gruppi un nome che rifletta lo scopo dei modelli stessi.

## <a name="related-topics"></a>Argomenti correlati

[Copiare le righe di modelli di assistenza](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]