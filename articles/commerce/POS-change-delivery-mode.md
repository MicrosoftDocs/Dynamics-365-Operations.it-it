---
title: Modifica modalità di consegna nel POS
description: Questo argomento descrive come configurare e utilizzare la modalità di modifica dell'operazione di consegna nel POS.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fd69d82536047c06e94ba4a7e860ef54680619a4
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193133"
---
# <a name="change-mode-of-delivery-in-pos"></a>Modifica modalità di consegna nel POS

[!include [banner](includes/banner.md)]

Questo argomento descrive come impostare e utilizzare la funzionalità "modifica modalità di consegna" nell'ambiente del punto vendita (POS). 

In Dynamics 365 Commerce versione 10.0.10 e successive, l'operazione **Cambia modalità di consegna** (647) è disponibile per l'aggiunta ai layout dello schermo del POS.

La funzione di modifica della modalità di consegna offre la possibilità di modificare la modalità di consegna per una o più linee di vendita configurate per la spedizione sulla transazione POS. Nelle versioni precedenti di Commerce, si doveva passare per intero i flussi della configurazione **Spedisci tutto** o **Spedizione selezionata** per modificare la modalità di consegna su una riga esistente configurata per la spedizione. Questo processo ha richiesto molto tempo e potrebbe comportare modifiche accidentali all'origine della consegna o alle date di consegna per la riga. La nuova funzionalità offre un metodo alternativo per l'aggiornamento efficiente della modalità di consegna su queste righe di vendita.

Per ulteriori informazioni su come aggiungere un'operazione a un pulsante sulla griglia dei pulsanti del POS, vedere [Layout dello schermo per il punto vendita](pos-screen-layouts.md).

Dopo aver configurato questa funzione nel POS, quando si seleziona **Cambia modalità di consegna**, verrà presentata una pagina di elenco che consente di scegliere le righe della transazione per cui si desidera modificare la modalità di consegna. È possibile scegliere alcune o tutte le righe o uscire senza apportare modifiche. Le righe di vendita precedentemente configurate per la spedizione sono le uniche righe nell'elenco che è possibile modificare. Se si desidera modificare una riga designata per il ritiro o il trasporto per la spedizione, è necessario utilizzare le operazioni **Spedisci tutto** o **Spedizione selezionata**. Al contrario, se si desidera modificare una riga designata come spedizione a un punto ritiro o un ritiro, è necessario utilizzare le operazioni **Preleva tutto**, **Preleva selezionato**, **Esegui tutto** o **Esegui selezionato**.

Dopo aver selezionato le righe che si desidera modificare, fare clic su **Cambia modalità di consegna** per visualizzare la richiesta di selezionare le opzioni della modalità di consegna. Se sono state selezionate più righe da modificare, il POS visualizzerà solo le modalità di consegna che sono state configurate come consentite per tutti i prodotti selezionati. Le modalità di consegna possono essere configurate per supportare prodotti e indirizzi di consegna specifici. Se esiste una modalità di consegna accettabile per una combinazione di prodotti e indirizzi ma non per un'altra combinazione di prodotti e indirizzi selezionata, la modalità di consegna non è disponibile. Potrebbe essere necessario selezionare le righe una per una e modificare separatamente la modalità di consegna per ciascuna riga se si desidera selezionare una modalità di consegna per un prodotto che non è supportato da un altro prodotto.  

Dopo aver selezionato la nuova modalità di consegna, viene visualizzata la pagina delle transazioni. Per rivedere le selezioni della nuova modalità di consegna, selezionare la scheda **Consegna** nell'elenco delle transazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare ordini servizio clienti](tasks/create-call-center-orders.md)

[Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]