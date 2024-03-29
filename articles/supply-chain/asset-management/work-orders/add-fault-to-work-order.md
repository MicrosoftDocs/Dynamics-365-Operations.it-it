---
title: Aggiungere errore all'ordine di lavoro
description: In questo articolo viene descritto come aggiungere registrazioni di errore agli ordini di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 210db3259a6c64a508119b30598a34dbda2d2dd2
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015000"
---
# <a name="add-fault-to-work-order"></a>Aggiungere errore all'ordine di lavoro

[!include [banner](../../includes/banner.md)]



È possibile aggiungere registrazioni di errore impostate in Designer errori a un ordine di lavoro. Uno o più record di errore devono essere collegati ai tipi di cespite utilizzati per il cespite selezionato nell'ordine di lavoro. Per ulteriori informazioni sull'impostazione, vedere [Gestione errori](../setup-for-work-orders/fault-management.md).

1. Seleziona **Gestione cespiti** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro per effettuare una registrazione dell'errore, quindi nel riquadro azioni, nella scheda **Ordine di lavoro**, nel gruppo **Cespite**, selezionare **Errore di cespite**.

3. Nella Scheda dettaglio **Sintomi** selezionare **Aggiungi riga**. Un numero di errore sequenziale viene automaticamente inserito nel campo **Errore**.

4. Selezionare il sintomo pertinente nel campo **Sintomo errore**.

5. Nei campi **Area di errore** e **Tipo di errore**, selezionare i valori appropriati.

6. La data corrente viene inserita automaticamente nel campo **Data errore**. È possibile selezionare una data diversa in base alle necessità.

7. Nella Scheda dettaglio **Cause del sintomo selezionato**, aggiungere una riga che descrive la causa del problema.

8. Nella Scheda dettaglio **Rimedi per sintomo selezionato**, aggiungere una riga che descrive una possibile soluzione per il problema.

9. Selezionare **Salva**.

Nella figura seguente viene illustrato un esempio di una registrazione dell'errore.

![Figura 1.](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Visualizzare gli errori registrati nei cespiti

Nell'elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti.

Nella pagina elenco **Errori di cespite**, è possibile ottenere una panoramica di tutti gli errori registrati nei cespiti. Per aprire la pagina, selezionare **Gestione cespiti** > **Richieste di informazioni** > **Errore di cespite** > **Errori di cespite**.


## <a name="print-asset-fault-report"></a>Stampare il report degli errori di cespite

Nella pagina elenco **Tutti i cespiti**, è possibile stampare un report degli errori di cespite contenente tutte le registrazioni di errore e una panoramica grafica delle statistiche degli errori.

1. Seleziona **Gestione cespiti** > **Cespiti** > **Tutti i cespiti**.

2. Selezionare tutti i cespiti per cui stampare il report degli errori.

3. Nel riquadro azioni, scheda **Generale**, gruppo **Report**, selezionare **Errore di cespite**.

4. Immettere un periodo specifico oppure selezionare un tipo di errore.

5. Selezionare **OK** per stampare il report.

>[!NOTE]
>Per stampare un report degli errori per vari cespiti o tipi di cespite, selezionare **Gestione cespiti** > **Report** > **Cespiti** > **Errore di cespite**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]