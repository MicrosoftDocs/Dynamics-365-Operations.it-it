---
title: Annulla ordini di assistenza
description: È possibile annullare un ordine di assistenza o una riga di ordine di assistenza a partire dall'ordine stesso oppure è possibile annullare più ordini di assistenza eseguendo un processo periodico.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228b76d6f6f0bb048662c8e82df76f51b7cb3652
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017378"
---
# <a name="cancel-service-orders"></a>Annulla ordini di assistenza   

[!include [banner](../includes/banner.md)]


È possibile annullare un ordine di assistenza o una riga di ordine di assistenza a partire dall'ordine stesso oppure è possibile annullare più ordini di assistenza eseguendo un processo periodico.


> [!NOTE]
> <P>Un ordine di assistenza non può essere annullato se la relativa fase non consente l'annullamento, se contiene richieste articoli o se è già stato registrato.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Annullare un ordine di assistenza nel modulo Ordini di assistenza

1.  Fai clic su **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**. Selezionare l'ordine di assistenza e fare clic su **Annulla ordine** nel riquadro azioni.

## <a name="cancel-a-service-order-line"></a>Annullare una riga di ordine di assistenza

1.  Fai clic su **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**. Fare doppio clic sull'ordine di assistenza contenente la riga che si desidera annullare.

2.  Selezionare la riga di ordine di assistenza che si desidera annullare, quindi fare clic su **Annulla riga ordine** per modificare lo stato della riga in **Annullata**.


> [!TIP]
> <P>Per revocare l'annullamento di una riga di ordine di assistenza e impostare di nuovo lo stato su <STRONG>Creato</STRONG>, fare clic su <STRONG>Revoca annullamento</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Annullare più ordini di assistenza

1.  Fare clic su **Gestione assistenza** \> **Periodico** \> **Ordini di assistenza** \> **Annulla ordini di assistenza**.

2.  Fare clic sul pulsante **Seleziona**.

3.  Nella colonna **Criteri** del modulo **Richiesta info** selezionare gli ordini di assistenza che si desidera annullare.

4.  Fare clic su **OK** per chiudere il modulo **Richiesta info**.

5.  Selezionare la casella di controllo **Mostra Registro informazioni** per generare un Registro informazioni in cui sono riportati gli ordini di assistenza annullati.

6.  Selezionare la casella di controllo **Revoca annullamento** se si desidera revocare lo stato **Annullato** di un ordine di assistenza.

7.  Fare clic su **OK**.

Gli ordini di assistenza selezionati verranno annullati o il relativo stato di avanzamento verrà reimpostato da **Annullato** a **In corso**.


> [!NOTE]
> <P>Se si seleziona la casella di controllo <STRONG>Revoca annullamento</STRONG>, gli ordini di assistenza con stato di avanzamento <STRONG>Annullato</STRONG> verranno revocati e quelli con stato di avanzamento <STRONG>In corso</STRONG> non verranno annullati.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]