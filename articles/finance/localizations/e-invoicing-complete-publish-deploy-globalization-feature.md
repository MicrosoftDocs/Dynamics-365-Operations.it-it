---
title: Completare, pubblicare e distribuire una funzionalità di globalizzazione
description: In questo articolo vengono fornite informazioni sul ciclo di vita delle funzionalità di globalizzazione.
author: gionoder
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 11378991a24e1a5f5e213d64f0f414db2e5c2573
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279902"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Completare, pubblicare e distribuire una funzionalità di globalizzazione

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Versioni della funzionalità di fatturazione elettronica

Viene effettuato il controllo delle versioni delle funzioni di fatturazione elettronica. Quando viene creata una nuova versione, il numero di versione viene incrementato automaticamente.

Le versioni delle funzionalità di fatturazione elettronica seguono un ciclo di vita che ha fino a tre stati:

- **Bozza** - Quando la versione di una funzionalità si trova in questo stato, è possibile modificare i suoi attributi di configurazione e i suoi artefatti (ad esempio, configurazioni del formato di file).
- **Completa** – Questo stato indica che hai finito di modificare la versione della funzionalità e non intendi apportare altri aggiornamenti. Quando la versione di una funzionalità ha questo stato, non è più possibile modificare la versione o i suoi componenti.
- **Pubblicata** - Questo stato indica che la versione della funzionalità è stata pubblicata nel repository globale associato alla propria organizzazione. Quando la versione di una funzionalità ha questo stato, non è più possibile modificare la versione o i suoi componenti.

È possibile specificare una **Data di inizio validità** per una nuova versione di una funzionalità di fatturazione elettronica. In questo modo è possibile definire una versione predefinita che può essere utilizzata o che può essere sovrascritta quando la funzionalità viene distribuita nell'ambiente del servizio.

Per modificare lo stato di una versione della funzionalità di fatturazione elettronica, attenersi alla seguente procedura.

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Nel lato sinistro della pagina **Funzionalità per la fatturazione elettronica**, seleziona la funzionalità per la fatturazione elettronica.
4. Nella scheda **Versioni** sul lato destro della pagina, seleziona la versione.
5. Seleziona **Modifica stato**, quindi seleziona **Completa** (se lo stato attuale è **Bozza**) o **Pubblicata** (se lo stato attuale è **Completa**).
6. Nella finestra del messaggio, seleziona **Sì** per confermare la richiesta.

La modifica manuale dallo stato **Completa** allo stato **Pubblicata** è facoltativa. Le versioni delle funzionalità di fatturazione elettronica vengono aggiornate automaticamente allo stato **Pubblicata** quando vengono distribuite nell'ambiente di servizio.

Puoi tener traccia dello stato nella colonna **Stato versione funzionalità** nella scheda **Versioni**.

## <a name="deploy-feature-versions"></a>Distribuire versioni delle funzionalità

In RCS, usi il comando **Distribuisci** per pubblicare una versione della funzionalità di fatturazione elettronica nell'ambiente del servizio di destinazione o nell'applicazione connessa.

1. Nel lato sinistro della pagina **Funzionalità per la fatturazione elettronica**, seleziona la funzionalità per la fatturazione elettronica.
2. Nella scheda **Versioni** sul lato destro della pagina, seleziona la versione della funzionalità di fatturazione elettronica che vuoi distribuire nell'ambiente di servizio o nell'applicazione connessa. La versione selezionata deve avere lo stato **Completa** o **Pubblicata**.
3. Seleziona **Distribuisci**, quindi seleziona una e entrambe le seguenti opzioni per definire la destinazione della distribuzione:

    - **Applicazione connessa** – La configurazione fornita dalla configurazione dell'applicazione viene scritta nell'istanza di Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management che era stato precedentemente associata ad essa.
    - **Ambiente di servizio** – La versione della funzionalità di fatturazione elettronica viene distribuita nell'ambiente di servizio. Fatturazione elettronica è quindi pronto per ricevere ed elaborare i documenti elettronici inviati da Finance o Supply Chain Management.

> [!NOTE]
> Di solito, cambierai i parametri della funzione di reporting elettronico (ER) che deve essere distribuita nell'ambiente di servizio. Le modifiche all'applicazione connessa saranno rare. È consigliabile distribuire le nuove versioni all'applicazione connessa solo quando modifichi i parametri corrispondenti della tua applicazione.

Per determinare se una versione specifica di una funzionalità di fatturazione elettronica viene distribuita in un ambiente specifico, rivedi le informazioni nella scheda **Ambienti**.

## <a name="remove-feature-versions"></a>Rimuovere le versioni delle funzionalità

In RCS, puoi selezionare **Annulla** per rimuovere una versione specifica della funzionalità di fatturazione elettronica da un ambiente del servizio se è stato distribuita in tale ambiente.

> [!IMPORTANT]
> Il pulsante **Annulla** funziona solo per gli ambienti di servizio. Non rimuove niente dalle applicazioni connesse per la funzionalità di fatturazione elettronica corrente.

## <a name="rebase-electronic-invoicing-features"></a>Riassegnare le funzionalità di fatturazione elettronica

Quando una funzione di fatturazione elettronica deriva da un'altra, puoi selezionare **Riassegna** per aggiornare la funzionalità derivata con le modifiche introdotte nella funzionalità originale (padre).

Per riassegnare una versione derivata di una funzionalità creata, attenersi alla seguente procedura.

1. Recupera l'ultima versione della funzionalità importandola dal repository globale. Per ulteriori informazioni, vedere [Importare la funzionalità dal repository globale](e-invoicing-import-feature-global-repository.md).
2. Nell'elenco delle funzionalità, selezionare la funzionalità da riassegnare.
3. Nella scheda **Versioni**, seleziona **Nuova** per creare una versione bozza.
4. Selezionare **Riassegna**.
5. Nella finestra di dialogo **Riassegna**, seleziona la versione a cui riassegnare la funzionalità.
6. Seleziona **OK**.
7. Esaminare i componenti della funzionalità e apportare le modifiche necessarie.
8. Selezionare **Cambia stato** per completare la funzionalità riassegnata. Una volta completata la riassegnazione, è possibile eseguire azioni aggiuntive.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Recuperare una versione specifica delle funzionalità di fatturazione elettronica

Quando crei una nuova versione di una funzionalità di fatturazione elettronica, il sistema crea una copia dell'ultima versione della funzionalità. Per utilizzare una versione precedente della funzionalità come base per una nuova versione, seleziona la versione, quindi seleziona **Recupera questo comando di versione**. Viene creata una nuova versione bozza della funzionalità che è una copia della versione selezionata.
