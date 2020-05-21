---
title: Creare modelli previsionali per budget di progetto
description: Questo argomento descrive come creare un modello previsionale per i budget residui.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
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
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321781"
---
# <a name="create-forecast-models-for-project-budgets"></a>Creare modelli previsionali per budget di progetto 

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare un modello previsionale per i budget residui. In un progetto soggetto al controllo del budget vengono utilizzati due tipi di budget: originale e residuo. Quando si crea un budget di progetto, è necessario specificare i modelli previsionali di budget originale e residuo creati nella pagina **Modelli previsionali**. I budget di progetto basati su modelli specifici vengono creati quando si esegue il commit del budget di progetto.

> [!NOTE]
> Un modello previsionale utilizzato per il controllo del budget non può avere un sottomodello né può essere utilizzato come sottomodello.

1. Selezionare **Gestione progetti e contabilità** > **Imposta** > **Previsioni**  > **Modelli previsionali**.
2. Seleziona **Nuovo** per creare un nuovo modello previsionale, quindi immettere un numero di ID modello e un nome per il nuovo modello. 
3. Impostare l'opzione **Arrestato** su **Sì** per impedire eventuali modifiche alle righe di previsione per il modello previsionale. 
4. Se dalle righe di previsione a cui è associalo il modello dovranno essere generate previsioni di cassa nella contabilità generale, impostare **Includere in previsioni di cassa** su **Sì**. 
5. Per utilizzare la data del progetto come data della fattura, impostare **Data fattura prevista** su **Sì**. 
6. Nel campo **Tipo di budget** selezionare uno dei seguenti tipi di modelli:

   - **Budget originale**: utilizzare gli importi del budget originale di cui viene eseguito il commit quando viene creato e approvato il budget iniziale.
   - **Budget residuo**: utilizzare questo tipo di modello per gli importi del budget residuo durante la vita utile del progetto. I saldi in questo modello previsionale vengono ridotti in base alle transazioni effettive e aumentati o diminuiti in base alle revisioni del budget.
   - **Riportabile in avanti**: utilizzare gli importi del budget riportabile in avanti per il progetto. Riportabile in avanti è un processo facoltativo e può essere eseguito per trasferire gli importi di budget inutilizzati da un anno fiscale a un altro.

7. Impostare le seguenti opzioni come richiesto:

   - Abilitare **Data fattura prevista** per utilizzare la data del progetto come data della fattura.
   - Abilitare **Previsioni con WIP** per eseguire le previsioni in base ai WIP (Work-in-Progress), quindi selezionare il tipo di WIP. 
   - È possibile mantenere il valore predefinito **Tipo di budget** come **Nessuno** o inserire un nuovo tipo. Il tipo di budget non può essere modificato dopo aver modificato un record.     
    > [!NOTE]
    > Se si modifica il tipo di budget predefinito, tutte le altre opzioni non saranno disponibili per gli aggiornamenti e non è possibile riutilizzare questo modello previsionale. 
   


 

