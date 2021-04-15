---
title: Aggiungere un codice a matrice o un codice a barre ai messaggi di posta elettronica transazionali e di ricevuta
description: In questo argomento viene descritto come inserire codici a matrice e codici a barre che rappresentano ID ordine nei messaggi di posta elettronica transazionali e di ricevuta in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797505"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a>Aggiungere un codice a matrice o un codice a barre ai messaggi di posta elettronica transazionali e di ricevuta

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento viene descritto come inserire codici a matrice e codici a barre che rappresentano ID ordine nei messaggi di posta elettronica transazionali e di ricevuta in Microsoft Dynamics 365 Commerce.

È possibile includere facilmente codici a matrice e codici a barre nei messaggi di posta elettronica transazionali per accelerare il processo di ricerca di ordini in un ambiente di vendita al dettaglio. Per inserire codici a matrice e codici a barre nei messaggi di posta elettronica, utilizzare un tag **\<img\>** HTML che richiede un'immagine del codice a matrice o del codice a barre di un servizio di generazione e rendering. Microsoft non fornisce questo servizio. Tuttavia, esistono molti servizi gratuiti o poco costosi che possono fornire codici a matrice o codici a barre generati dinamicamente in base a un valore passato in una stringa di query.

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a>Aggiungere un codice a matrice o un codice a barre a un messaggio di posta elettronica transazionale

Per inserire un codice a matrice o un codice a barre in un messaggio di posta elettronica transazionale inviato come parte di un acquisto e-commerce, seguire questi passaggi.

1. Apri l'HTML di origine per il modello di messaggio di posta elettronica transazionale e aggiungere un tag **\<img\>** HTML che punta al servizio di codici a matrice o codici a barre. Ecco un esempio.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    Di seguito è riportata una dell'esempio precedente:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** rappresenta il dominio del servizio di codici a matrice o codici a barre.
    - **data** rappresenta il parametro utilizzato dal servizio di codici a matrice o codici a barre per ricevere il contenuto di cui deve essere eseguito il rendering come codice a matrice o codice a barre.

        Il valore **%salesid%** deve essere assegnato a questo parametro. In questo esempio, si noti che il valore viene utilizzato anche come testo alternativo dell'immagine.

    - **param1** e **param2** rappresentano parametri facoltativi aggiuntivi.

1. Selezionare **Retail e Commerce \> Impostazione sedi centrali \> Parametri\> Modelli di posta elettronica a livello di organizzazione** e caricare l'HTML aggiornato nel modello di messaggio di posta elettronica transazionale appropriato.

> [!NOTE]
> I parametri potrebbero differire tra i provider di servizi di codici a matrice e codici a barre. Pertanto, assicurarsi di contattare il provider di servizi per confermare i parametri a cui è necessario assegnare i valori.

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a>Aggiungere un codice a matrice o un codice a barre a un messaggio di posta elettronica di ricevuta 

Per inserire un codice a matrice o un codice a barre in un messaggio di posta elettronica di ricevuta che può essere inviato dopo aver effettuato un acquisto presso il punto vendita (POS), seguire questi passaggi.

1. Aprire l'HTML di origine per il modello di messaggio di posta elettronica di ricevuta e aggiungere un tag **\<img\>** HTML che punta al servizio di codici a matrice o codici a barre. Di seguito è riportato un esempio.

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    Di seguito è riportata una dell'esempio precedente:

    - **YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** rappresenta il dominio del servizio di codici a matrice o codici a barre.
    - **data** rappresenta il parametro utilizzato dal servizio di codici a matrice o codici a barre per ricevere il contenuto di cui deve essere eseguito il rendering come codice a matrice o codice a barre.

        Il valore **%receiptid%** deve essere assegnato a questo parametro. In questo esempio, si noti che il valore viene utilizzato anche come testo alternativo dell'immagine.

    - **param1** e **param2** rappresentano parametri facoltativi aggiuntivi.

1. Selezionare **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione** e caricare l'HTML aggiornato nel modello di messaggio di posta elettronica il cui ID posta elettronica è **emailrecpt**.

> [!NOTE]
> I parametri potrebbero differire tra i provider di servizi di codici a matrice e codici a barre. Pertanto, assicurarsi di contattare il provider di servizi per confermare i parametri a cui è necessario assegnare i valori.

## <a name="additional-resources"></a>Risorse aggiuntive

[Inviare le ricevute tramite posta elettronica da Modern POS (MPOS)](email-receipts.md)

[Creare modelli e-mail per eventi transazionali](email-templates-transactions.md)
