---
title: Registrare il consumo
description: In questo argomento viene illustrato come registrare il consumo in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c9bbd51da23ea412bc124f932f73876a9506d47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431262"
---
# <a name="register-consumption"></a>Registrare il consumo

[!include [banner](../../includes/banner.md)]

 

Dopo il completamento di un ordine di lavoro, è necessario eseguire le registrazioni del consumo e registrare i giornali di registrazione. È possibile effettuare registrazioni per i seguenti tipi di consumo: ore, articoli e spese. I differenti tipi di consumo vengono registrati nella pagina **Giornali di registrazione ordine di lavoro**. La configurazione dei giornali di registrazione in **Gestione cespiti** viene utilizzata per creare e registrare giornali di registrazione distinti per ore, articoli e spese nel modulo **Gestione progetti e contabilità**.

In alcuni casi, esiste la possibilità di aggiungere o eliminare righe di previsione, ma ciò dipende dall'impostazione dello stato del ciclo di vita di ordine di lavoro, dal tipo di progetto correlato e dalla regole di fase associate. Per ulteriori informazioni sugli stati del ciclo di vita di ordine di lavoro e sulle fasi di progetto correlate, vedere [Previsioni, ordini di lavoro e progetti](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>È possibile impostare la registrazione automatica dei giornali di registrazione in uno stato del ciclo di vita di ordine di lavoro. Per ulteriori informazioni, fare riferimento a [Stati del ciclo di vita ordine di lavoro](../setup-for-work-orders/work-order-lifecycle-states.md).

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.

3. Fare clic su **Copia da previsione** per trasferire le eventuali righe di previsione che possono essere associate all'ordine di lavoro. È possibile selezionare i tipi di consumo che si desidera trasferire.

4. Se necessario, è possibile aggiungere ulteriori righe di consumo nella Scheda dettaglio pertinente facendo clic su **Aggiungi riga** e immettendo i dati nella riga.

5. Fare clic su **Convalida giornali di registrazione** per convalidare le righe dei giornali di registrazione prima della registrazione.

6. Fare clic su **Registra giornali** per registrare le righe dei giornali di registrazione.

7. Dopo aver registrato i giornali di registrazione consumo, è possibile aggiornare lo stato del ciclo di vita dell'ordine di lavoro. Ad esempio, per indicare che l'ordine di lavoro è completato, è possibile aggiornare lo stato del ciclo di vita in "Finito".

    - Nel campo **Mostra** nella parte superiore della pagina **Giornali di registrazione ordine di lavoro**, selezionare le righe dei giornali di registrazione che si desidera visualizzare: **Tutto**, **Non registrato** o **Registrato**. I giornali di registrazione registrati presentano un segno di spunta nella casella di controllo **Registrato**.  
    - Quando si creano righe articolo nel giornale di registrazione di ordine di lavoro, le dimensioni prodotto e le dimensioni di tracciabilità correlate all'articolo sono trasferite automaticamente alla riga del giornale di registrazione.  

La schermata seguente mostra un esempio di registrazioni di ore e articoli in un ordine di lavoro in **Giornali di registrazione ordine di lavoro**.

![Figura 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Suddividere le ore negli ordini di lavoro con più processi di ordine di lavoro

Se un ordine di lavoro contiene più processi di ordine di lavoro, è possibile registrare le ore lavorative utilizzando la funzionalità **Suddividi ore**, nel senso che la riga di registrazione di 1 ora può essere distribuita in modo uniforme in ogni processo di ordine di lavoro.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro e fare clic su **Giornali di registrazione**.

3. Selezionare la riga di registrazione ore che si desidera suddividere e fare clic su **Suddividi ore**.

4. Nella finestra di dialogo **Suddividi ore in processi di manutenzione ordine di lavoro**, il nome del lavoratore che ha effettuato l'accesso viene visualizzato automaticamente nel campo **Lavoratore**. Se necessario, è possibile selezionare un altro lavoratore.

5. Selezionare una categoria per la registrazione ore nel campo **Categoria**.

6. Nel campo **Ore** inserire il numero di ore da suddividere.

    ![Figura 2](media/02-consumption.png)

7. Fare clic su **OK**.

*Esempio:* nella schermata seguente sono visualizzate le righe del giornale di registrazione per un ordine di lavoro contenente tre processi di ordine di lavoro. La prima riga, contenente tre ore lavorative, è stata suddivisa e un'ora lavorativa è registrata in ciascun processo di ordine di lavoro. Dopo la creazione della registrazione delle tre ore, è necessario decidere cosa fare con la riga di registrazione ore originale (la prima riga nell'esempio). È possibile tenerla così com'è oppure eliminarla. 

![Figura 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Dimensioni finanziarie nelle registrazioni del consumo

Quando si eseguono registrazioni del consumo, le dimensioni finanziarie relative ai differenti tipi di registrazione vengono aggiunte alle registrazioni in una sequenza specifica. 

- *Registrazioni ore e spese:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione. Successivamente, vengono aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato. Infine, vengono aggiunte le dimensioni finanziarie dalla risorsa (lavoratore).

- *Registrazioni articoli:* innanzi tutto, vengono aggiunte le eventuali dimensioni finanziarie dall'intestazione del giornale di registrazione. Vengono quindi aggiunte le dimensioni finanziarie dal progetto di ordine di lavoro correlato. Successivamente, vengono aggiunte le dimensioni finanziarie dal sito. Infine, vengono aggiunte le dimensioni finanziarie dall'articolo.

>[!NOTE]
>Per tutti e tre i tipi di registrazione, viene convalidata la combinazione di dimensioni finanziarie e le combinazioni non valide vengono lasciate vuote. Questa è la configurazione standard con altre app Finance and Operations.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]