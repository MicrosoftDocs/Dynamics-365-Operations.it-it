---
title: Sincronizzare valutazioni di prodotti in Dynamics 365 Retail
description: In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698167"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a>Sincronizzare valutazioni di prodotti in Dynamics 365 Retail

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Retail.

## <a name="overview"></a>Panoramica

Per utilizzare valutazioni di prodotti nei multicanali, ad esempio nel POS e nei servizi clienti, le valutazioni di prodotti del servizio Valutazioni e recensioni devono essere importate nel database del canale di Retail. Quando le valutazioni di prodotti diventano disponibili nei multicanali, possono aiutare indirettamente i clienti durante le interazioni con gli addetti alle vendite.

In questo argomento vengono descritte le seguenti attività:

1. Configurare un processo batch di Retail per importare valutazioni di prodotti.
1. Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente.
1. Rendere le valutazioni di prodotti disponibili nel POS.

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a>Configurare un processo batch di Retail per importare valutazioni di prodotti

> [!IMPORTANT]
> Prima di iniziare, assicurarsi che sia installata la versione 10.0.6 o successiva di Retail.

### <a name="initialize-the-retail-scheduler"></a>Inizializzare Retail Scheduler

Per inizializzare Retail Scheduler, effettuare le operazioni indicate di seguito.

1. Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Inizializza Retail Scheduler**. In alternativa, cercare "Inizializza Retail Scheduler".
1. Nella finestra di dialogo **Inizializza Retail Scheduler**, verificare che l'opzione **Elimina configurazione esistente** sia impostata su **No** e selezionare **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Verificare il processo secondario RetailProductRating

Per verificare che il processo secondario **RetailProductRating** esista, effettuare le seguenti operazioni.

1. Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Processi secondari Retail Scheduler**. In alternativa, cercare "Processi secondari Retail Scheduler".
1. Nell'elenco di processi secondari, trovare o cercare il processo secondario **RetailProductRating**.

Nella figura seguente è illustrato un esempio dei dettagli del processo secondario in Retail.

![Dettagli del processo secondario RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Se non si trova il processo secondario **RetailProductRating**, è possibile che il processo **Sincronizzare valutazioni di prodotti** e il processo **1040 CDX** siano già stati eseguiti prima di inizializzare Retail Scheduler. In tal caso, effettuare le operazioni indicate di seguito per eseguire il processo **Sincronizzazione dati completa**.
>
> 1. Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Database canale**. In alternativa, cercare "Database canale".
> 1. Selezionare il database del canale da sincronizzare.
> 1. Selezionare **Sincronizzazione dati completa** nel riquadro azioni.
> 1. Nella finestra di dialogo a discesa **Seleziona programmazione distribuzione** selezionare **1040 - prodotti**, e quindi **OK**.
> 1. Ripetere i passaggi della procedura precedente per verificare che il processo secondario **RetailProductRating** sia stato creato.

### <a name="import-product-ratings"></a>Importare valutazioni di prodotti

Per importare valutazioni di prodotti in Retail dal servizio Salutazioni e recensioni, effettuare le seguenti operazioni.

1. Andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Retail Scheduler \> Processo Sincronizza valutazioni di prodotti**. In alternativa, cercare "Processo Sincronizza valutazioni di prodotti".
1. Nella finestra di dialogo **Esegui pull di valutazioni di prodotti**, nella Scheda dettaglio **Esecuzione in background**, selezionare **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza**, impostare un criterio di ricorrenza (il valore suggerito è due ore). Non programmare una ricorrenza inferiore a un'ora.
1. Selezionare **OK**.
1. Impostare l'opzione **Processo batch** su **Sì**. Questa impostazione assicura la possibilità di esaminare i log e di verificare lo stato delle esecuzioni dei processi batch.
1. Selezionare **OK** per programmare il processo batch.

Nella figura seguente è illustrato un esempio di configurazione di processo batch in Retail.

![Configurazione del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente

Per verificare l'esito positivo del processo batch **Sincronizza valutazioni di prodotti**, effettuare le operazioni indicate di seguito.

1. Andare a **Vendita al dettaglio \> Amministratore di sistema \> Informazioni \> Processi batch** oppure, se si utilizza un'unità di stockkeeping solo di Retail, andare a **Vendita al dettaglio \> Richieste di informazioni e report \> Processi batch**. In alternativa, cercare "Processi batch".
1. Per visualizzare i dettagli del processo batch, nell'elenco dei processi batch, nella colonna **Descrizione processo**, cercare una descrizione che contiene "Esegui pull di valutazioni di prodotti".
1. Selezionare l'ID processo per visualizzare i dettagli del processo batch, come la data e l'ora di inizio pianificate e il testo di ricorrenza.

Nella figura seguente è illustrato un esempio di dettagli di un processo batch in Retail quando l'esecuzione del processo batch deve avvenire ogni due ore.

![Dettagli del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Rendere le valutazioni di prodotti disponibili nel POS

Il servizio Valutazioni e recensioni in Dynamics 365 Commerce è una soluzione multicanale. Tuttavia, le valutazioni di prodotti non sono visualizzate nel POS per impostazione predefinita. Per consentire ai clienti nei punti vendita di visualizzare valutazioni e recensioni quando interagiscono con gli addetti alle vendite, è necessario attivare le valutazioni di prodotti nel POS.

Per attivare le valutazioni di prodotti nel POS, effettuare le seguenti operazioni.

1. Accedere a **Vendita al dettaglio \> Impostazioni vendita al dettaglio \> Parametri \> Parametri di vendita al dettaglio**. In alternativa, cercare "Parametri di vendita al dettaglio".
1. Nella scheda **Parametri di configurazione**, selezionare **Nuovo**.
1. Immettere un nome ad esempio **RatingsAndReviews.EnableProductRatingsForRetailStores** e impostare il valore su **true**.
1. Selezionare **Salva**.
1. Andare a **Vendita al dettaglio \> Vendita al dettaglio IT \> Programmazione della distribuzione**. In alternativa, cercare "Programmazione della distribuzione".
1. Nell'elenco dei processi, selezionare **1110** (**Configurazione globale**) e quindi **Esegui adesso**.
1. Dopo la corretta esecuzione del processo, verificare che le valutazioni di prodotti siano visualizzate nel POS.

Nella figura seguente è illustrato un esempio di configurazione dei parametri di vendita al dettaglio per attivare le valutazioni di prodotti nel POS.

![Configurazione dei parametri di vendita al dettaglio per la valutazioni di prodotti nel POS](media/rnr-hq-enable-ratings-in-pos.png)

Di seguito viene illustrato un esempio delle valutazioni di prodotti nel POS.

![Valutazioni di prodotti nel POS](media/rnr-pos-catalog-ratings.png)

Di seguito viene illustrato un esempio delle valutazioni di prodotti nei canali del servizio clienti.

![Valutazioni di prodotti in un canale del servizio clienti](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e recensioni](ratings-reviews-overview.md)

[Consentire l'utilizzo di valutazioni e recensioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e recensioni](manage-reviews.md)

[Configurare valutazioni e recensioni](configure-ratings-reviews.md)
