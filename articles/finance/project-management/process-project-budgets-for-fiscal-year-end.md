---
title: Trasferire budget di progetto a fine anno fiscale
description: Questo articolo fornisce informazioni su come trasferire gli importi di budget rimanenti negli anni futuri e creare i dettagli del registro di budget.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172332"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Trasferire budget di progetto a fine anno fiscale

[!include [banner](../includes/banner.md)]

Quando si utilizza su un progetto pluriennale, è possibile che vi sia budget rimanente alla fine dell'anno fiscale. È possibile trasferire gli importi a budget residui per un anno futuro e creare dettagli del registro di budget per gli importi nella contabilità generale associata. Prima di riportare gli importi rimanenti, rivedere e analizzare gli importi di budget rimanenti.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Rivedere e analizzare gli importi con budget residui

Completare i seguenti passaggi per esaminare gli importi budget di fine anno per i progetti, ma non si desidera riportare gli importi.

1. Andare a **Gestione progetti e contabilità** > **Periodico** > **Saldi** > **Budget riportabile in avanti**. 
2. Nella pagina **Processo di riporto budget di progetto**, nella scheda **Opzioni di fine anno**, verificare che **Riporta importi budget di progetto residui** non sia abilitato.
3. Nella scheda **Parametri**, nel campo **Anno budget di progetto**, selezionare l'anno fiscale per cui visualizzare gli importi di budget residui. 
4. Nel campo **Anno fiscale di apertura** selezionare l'anno fiscale per il quale si desidera visualizzare l'importo a budget residuo. 
5. Nel campo **Dal modello di previsione**, selezionare **Budget residuo**. 
6. Per includere progetti che soddisfano i criteri selezionati e che non hanno budget residui, selezionare **Visualizza valori zero rimanenti**.  
7. Nella scheda **Seleziona budget**, selezionare **Recupera tutti i budget** per caricare tutti i budget corrispondenti ai criteri selezionati, quindi selezionare **Elabora**. 
8. Per progettare una query di database che carica un set specifico di budget nel riquadro, fare clic su **Recupera budget selezionati**.

Per ulteriori informazioni su una riga specifica nel riquadro, selezionare la riga, quindi selezionare **Visualizza dettagli budget** o **Visualizza conti**.

## <a name="carry-forward-remaining-budget-amounts"></a>Riportare importi a budget residuo 

Quando si elaborano gli importi a budget residui, è possibile creare transazioni di contabilità generale per gli importi riportati. Per creare transazioni di contabilità generale, completare i passaggi nella sezione [Riportare gli importi a budget creando transazioni di contabilità generale](#carry-forward). 

> [!NOTE]
> Gli importi a budget riportati vengono trasferiti al modello previsionale selezionato nella pagina **Modelli previsionali** come modello previsionale di riporto.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Riportare gli importi a budget creando transazioni di contabilità generale

1.  Selezionare **Gestione progetti e contabilità** > **Periodico** > **Saldi** > **Budget riportabile in avanti**. 
2. Nella pagina**Processo di riporto budget di progetto**, selezionare **Fine anno** e quindi abilitare **Riporta importi budget di progetto residui** e **Crea voci del registro di budget in contabilità generale**. 
3. Nella scheda **Parametri**, nel gruppo di campi **Parametri di progetto**, selezionare quanto segue:

   - **Anno budget di progetto**: selezionare l'inizio dell'anno fiscale per il quale si desidera visualizzare gli importi a budget residui. 
   - **Profitti e perdite**: creare transazioni di profitti e perdite nella contabilità generale. 
   -  **WIP**: creare transazioni Work in Progress (WIP) nella contabilità generale.
   -  **Retribuzioni**: creare transazioni di allocazione retribuzioni nella contabilità generale. 

5. Nel gruppo di campi **Contabilità generale** fornire le informazioni seguenti: 

   - Nel campo **Anno fiscale di apertura** selezionare l'inizio dell'anno fiscale al quale si desidera trasferire gli importi a budget residui per i progetti. Il valore predefinito è l'anno successivo a quello indicato nel valore del campo **Anno budget di progetto**.
   -  Nel campo **Periodo riportabile** selezionare il periodo in cui si desidera creare i dettagli del registro di budget nella contabilità generale. Si tratta in genere del primo periodo dell'anno fiscale che si sta aprendo.

6. Nel gruppo di campi **Copia in/da** fornire le informazioni seguenti:

   - Nel campo **Dal modello di previsione** selezionare il modello previsionale di progetto associato agli importi a budget residui che si desidera trasferire per i progetti. 
   - Nel campo **Al modello di di budget contabile** selezionare il modello di budget contabile associato agli importi a budget che si desidera trasferire alla contabilità generale. 
   -  Selezionare **Valuta vendita trasferimento** per utilizzare la valuta di vendita del progetto per le transazioni di contabilità generale create quando si trasferiscono gli importi del budget per i progetti. Quando l'opzione non è selezionata, le transazioni utilizzano la valuta contabile. 
   -  Selezionare **Visualizza valori zero rimanenti** per includere progetti che non hanno importi di budget residui, ma che soddisfano gli altri criteri selezionati nei progetti visualizzati nel riquadro inferiore.

7. Nella scheda **Seleziona budget**, selezionare **Recupera tutti i budget** per caricare tutti i budget corrispondenti ai criteri selezionati. Per progettare una query di database che carica un set specifico di budget di progetto nel riquadro, fare clic su **Recupera budget selezionati**.
8. Per ciascun progetto che si desidera elaborare, selezionare l'opzione all'inizio della riga per il progetto.

    > [!TIP]
    > Per selezionare tutti o la maggior parte dei progetti, selezionare il segno di spunta nell'angolo in alto a sinistra. Per escludere l'elaborazione di qualsiasi progetto, deselezionare il segno di spunta per quel progetto.

9. Per trasferire gli importi a budget residui per i progetti selezionati all'anno fiscale selezionato e per creare dettagli del registro di budget nella contabilità generale, selezionare **Elabora**.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Riportare gli importi a budget senza creare transazioni di contabilità generale

1. Andare a **Gestione progetti e contabilità** > **Periodico** > **Saldi** > **Budget riportabile in avanti**.
2. Nella pagina **Processo di riporto budget di progetto**, nella campo **Opzioni di fine anno**, selezionare **Riporta importi budget di progetto residui**.
3. Nel gruppo **Parametri**, nel campo **Anno budget di progetto**, selezionare l'anno fiscale per cui visualizzare gli importi di budget residui.
4. Nel gruppo **Copia in/da** fornire le informazioni seguenti:

   - Nel campo **Dal modello di previsione** selezionare il modello previsionale di progetto associato agli importi a budget residui che si desidera trasferire per i progetti. 
   - Selezionare **Visualizza valori zero rimanenti** per includere progetti che soddisfano i criteri selezionati e che non hanno budget residui.
   - Nel gruppo **Seleziona budget**, selezionare **Recupera tutti i budget** per caricare tutti i budget corrispondenti ai criteri selezionati. Per progettare una query di database che carica un set specifico di budget di progetto nel riquadro, fare clic su **Recupera budget selezionati**.

5. Per ciascun progetto che si desidera elaborare, selezionare l'opzione all'inizio della riga per il progetto. 
6. Selezionare **Elabora** per trasferire gli importi a budget residui per i progetti selezionati all'anno fiscale selezionato.

