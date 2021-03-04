---
title: Sincronizzare valutazioni sul prodotto in Dynamics 365 Commerce
description: In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
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
ms.openlocfilehash: dec87b548f3a218e1f833b752305f373e893b14c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413523"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>Sincronizzare valutazioni sul prodotto in Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come sincronizzare valutazioni di prodotti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Per utilizzare valutazioni di prodotti nei multicanali, ad esempio nel POS e nei servizi clienti, le valutazioni di prodotti del servizio Valutazioni e recensioni devono essere importate nel database del canale di Commerce. Quando le valutazioni di prodotti diventano disponibili nei multicanali, possono aiutare indirettamente i clienti durante le interazioni con gli addetti alle vendite.

In questo argomento vengono descritte le seguenti attività:

1. Configurare **Processo di sincronizzazione valutazioni prodotti** come processo batch per sincronizzare le valutazioni sui prodotti dal **Servizio di valutazioni e recensioni**.
1. Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente.
1. Rendere le valutazioni di prodotti disponibili nel POS.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Configurare un processo batch per sincronizzare valutazioni di prodotti

> [!IMPORTANT]
> Prima di iniziare, assicurarsi che sia installata la versione 10.0.6 o successiva di Dynamics 365 Commerce.

### <a name="initialize-the-commerce-scheduler"></a>Inizializzare l'utilità di pianificazione di commercio

Per inizializzare l'utilità di pianificazione di commercio, effettuare le operazioni indicate di seguito.

1. Andare a **Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Inizializza utilità di pianificazione di commercio**. In alternativa, cercare "Inizializza utilità di pianificazione di commercio".
1. Nella finestra di dialogo **Inizializza utilità di pianificazione di commercio**, verificare che l'opzione **Elimina configurazione esistente** sia impostata su **No** e selezionare **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Verificare il processo secondario RetailProductRating

Per verificare che il processo secondario **RetailProductRating** esista, effettuare le seguenti operazioni.

1. Andare a **Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Processi secondari unità di pianificazione**. In alternativa, cercare "Processi secondari Retail Scheduler".
1. Nell'elenco di processi secondari, trovare o cercare il processo secondario **RetailProductRating**.

Nella figura seguente è illustrato un esempio dei dettagli del processo secondario in Commerce.

![Dettagli del processo secondario RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Se non si trova il processo secondario **RetailProductRating**, è possibile che il processo **Sincronizzare valutazioni di prodotti** e il processo **1040 CDX** siano già stati eseguiti prima di inizializzare l'utilità di pianificazione di commercio. In tal caso, effettuare le operazioni indicate di seguito per eseguire il processo **Sincronizzazione dati completa**.

> 1. Andare a **Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Database canale**. In alternativa, cercare "Database canale".
> 1. Selezionare il database del canale da sincronizzare.
> 1. Nel riquadro azioni selezionare **Sincronizzazione dati completa**.
> 1. Nella finestra di dialogo a discesa **Seleziona programmazione distribuzione** selezionare **1040 - prodotti**, e quindi **OK**.
> 1. Ripetere i passaggi della procedura precedente per verificare che il processo secondario **RetailProductRating** sia stato creato.

### <a name="import-product-ratings"></a>Importare valutazioni di prodotti

Per importare valutazioni di prodotti in Commerce dal servizio Valutazioni e recensioni, effettuare le seguenti operazioni.

1. Andare a **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Unità di pianificazione di commercio \> Processo Sincronizza valutazioni di prodotti**. In alternativa, cercare "Processo Sincronizza valutazioni di prodotti".
1. Nella finestra di dialogo **Esegui pull di valutazioni di prodotti**, nella Scheda dettaglio **Esecuzione in background**, selezionare **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza**, impostare un criterio di ricorrenza (il valore suggerito è due ore). Non programmare una ricorrenza inferiore a un'ora.
1. Selezionare **OK**.
1. Impostare l'opzione **Processo batch** su **Sì**. Questa impostazione assicura la possibilità di esaminare i log e di verificare lo stato delle esecuzioni dei processi batch.
1. Selezionare **OK** per programmare il processo batch.

Nella figura seguente è illustrato un esempio di configurazione di processo batch in Commerce.

![Configurazione del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Verificare che il processo batch per la sincronizzazione delle valutazioni di prodotti sia stato eseguito correttamente

Per verificare l'esito positivo del processo batch **Sincronizza valutazioni di prodotti**, effettuare le operazioni indicate di seguito.

1. Andare a **Retail e Commerce \> Amministratore di sistema \> Informazioni \> Processi batch** oppure, se si utilizza un'unità di stockkeeping solo di Commerce, andare a **Retail e Commerce \> Richieste di informazioni e report \> Processi batch**. In alternativa, cercare "Processi batch".
1. Per visualizzare i dettagli del processo batch, nell'elenco dei processi batch, nella colonna **Descrizione processo**, cercare una descrizione che contiene "Esegui pull di valutazioni di prodotti".
1. Selezionare l'ID processo per visualizzare i dettagli del processo batch, come la data e l'ora di inizio pianificate e il testo di ricorrenza.

Nella figura seguente è illustrato un esempio di dettagli di un processo batch in Commerce quando l'esecuzione del processo batch deve avvenire ogni due ore.

![Dettagli del processo batch Sincronizza valutazioni di prodotti](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Rendere le valutazioni di prodotti disponibili nel POS

Il servizio Valutazioni e recensioni in Dynamics 365 Commerce è una soluzione multicanale. Tuttavia, le valutazioni di prodotti non sono visualizzate nel POS per impostazione predefinita. Per consentire ai clienti nei punti vendita di visualizzare valutazioni e recensioni quando interagiscono con gli addetti alle vendite, è necessario attivare le valutazioni di prodotti nel POS.

Per attivare le valutazioni di prodotti nel POS, effettuare le seguenti operazioni.

1. Andare a **Retail e Commerce \> Impostazione Commerce \> Parametri \> Parametri di commercio**. In alternativa, cercare "Parametri di commercio".
1. Nella scheda **Parametri di configurazione**, selezionare **Nuovo**.
1. Immettere un nome ad esempio **RatingsAndReviews.EnableProductRatingsForRetailStores** e impostare il valore su **true**.
1. Selezionare **Salva**.
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**. In alternativa, cercare "Programmazione della distribuzione".
1. Nell'elenco dei processi, selezionare **1110** (**Configurazione globale**) e quindi **Esegui adesso**.
1. Dopo la corretta esecuzione del processo, verificare che le valutazioni di prodotti siano visualizzate nel POS.

Nella figura seguente è illustrato un esempio di configurazione dei parametri di commercio per attivare le valutazioni di prodotti nel POS.

![Configurazione dei parametri di commercio per la valutazioni di prodotti nel POS](media/rnr-hq-enable-ratings-in-pos.png)

Di seguito viene illustrato un esempio delle valutazioni di prodotti nel POS.

![Valutazioni di prodotti nel POS](media/rnr-pos-catalog-ratings.png)

Di seguito viene illustrato un esempio delle valutazioni di prodotti nei canali servizio clienti.

![Valutazioni di prodotti in un canale servizio clienti](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e recensioni](ratings-reviews-overview.md)

[Consentire l'utilizzo di valutazioni e recensioni](opt-in-ratings-reviews.md)

[Gestire valutazioni e recensioni](manage-reviews.md)

[Configurare valutazioni e recensioni](configure-ratings-reviews.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]