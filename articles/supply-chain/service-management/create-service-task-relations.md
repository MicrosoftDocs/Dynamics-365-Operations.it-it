---
title: Creare relazioni di attività di assistenza tecnica
description: È possibile associare le attività di assistenza tecnica a contratti di assistenza o ordini di assistenza in modo da descrivere l'attività di assistenza tecnica da completare per il contratto o l'ordine.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51ea26a0f6519d26f5207a7b6c8afbcdfa358be9
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015261"
---
# <a name="create-service-task-relations"></a>Creare relazioni di attività di assistenza tecnica    

[!include [banner](../includes/banner.md)]

È possibile associare le attività di assistenza tecnica a contratti di assistenza o ordini di assistenza in modo da descrivere l'attività di assistenza tecnica da completare per il contratto o l'ordine. Queste informazioni sono disponibili ai tecnici e ai clienti.

## <a name="create-a-relation-with-a-service-agreement"></a>Creare una relazione con un contratto di assistenza

1.  Seleziona **Gestione assistenza** \> **Contratti di assistenza** \> **Contratti di assistenza**.

2.  Selezionare un contratto di assistenza esistente o crearne uno nuovo.

3.  Nel riquadro azioni selezionare il pulsante **Attività di assistenza tecnica**.

4.  Nel modulo **Attività di assistenza tecnica** selezionare **Nuovo** per creare una nuova riga, quindi selezionare dall'elenco **Attività di assistenza tecnica** l'attività di assistenza tecnica da collegare al contratto di assistenza.

5.  Nella scheda **Descrizione** immettere le descrizioni di note interne o esterne nei campi a testo libero.

6.  Chiudere il modulo per salvare il record.

Ripetere la procedura finché non saranno state create tutte le relazioni di attività di assistenza tecnica necessarie per il contratto di assistenza. Sarà quindi possibile specificare queste attività da qualsiasi riga del contratto collegato.

Una relazione di attività di assistenza tecnica creata in un contratto di assistenza è disponibile da tutti gli ordini di assistenza collegati a quel contratto.

## <a name="create-a-relation-with-a-service-order"></a>Creare una relazione con un ordine di assistenza

1.  Vai a **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Selezionare un ordine di assistenza esistente o crearne uno nuovo.

3.  Nel riquadro azioni selezionare il pulsante **Attività di assistenza tecnica**.

4.  Nel modulo **Attività di assistenza tecnica** selezionare **Nuovo** per creare una nuova riga, quindi selezionare dall'elenco **Attività di assistenza tecnica** le attività di assistenza tecnica da collegare all'ordine di assistenza.

5.  Nella scheda **Descrizione** immettere le descrizioni di note interne o esterne nei campi a testo libero.

6.  Chiudere il modulo per salvare il record.

Ripetere la procedura finché non saranno state create tutte le relazioni di attività di assistenza tecnica necessarie per l'ordine di assistenza. Sarà quindi possibile, quando si creano righe dell'ordine di assistenza, selezionare l'attività per la quale è stata creata la relazione.

Le relazioni di attività di assistenza tecnica create in un ordine di assistenza sono disponibili nell'ordine stesso.

## <a name="see-also"></a>Vedere anche

[Panoramica attività di servizio](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]