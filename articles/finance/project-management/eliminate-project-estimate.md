---
title: Eliminare una stima di progetto
description: Questo argomento fornisce informazioni sull'eliminazione di una stima di progetto dopo che è stata completata.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410234"
---
# <a name="eliminate-a-project-estimate"></a>Eliminare una stima di progetto

[!include [banner](../includes/banner.md)]

Le stime di progetto forniscono un quadro finanziario del lavoro stimato e programmato per un progetto. Per utilizzare le stime in un progetto, è necessario associare il progetto a un progetto stima. Un progetto stima si basa sempre su un progetto esistente, ma più progetti possono fare riferimento a un singolo progetto stima. Solo i progetti a prezzo fisso e di investimento possono essere associati a progetti stima e tali progetti devono appartenere allo stesso gruppo di progetti del progetto stima.

Per eliminare un progetto stima, è necessario che questo sia stato completato. I seguenti passaggi consentono di eliminare una stima.

1. Passare a **Gestione progetti e contabilità** > **Tutti i progetti** e aprire il progetto. 
2. Nella scheda **Gestisci**, selezionare **Stime** e nella pagina **Stima** selezionare **Elimina**.
3. Nella pagina **Elimina stima** della scheda **Generale**, imposta le seguenti opzioni:

   - **Codice periodo**: selezionare il codice del periodo per scegliere i progetti stima appropriati. 
   - **Data stima**: selezionare la data di stima appropriata per l'eliminazione.
   - **Elimina con avvisi WIP**: abilitare questa opzione per fornire una notifica quando verrà eliminata una stima associata a un work in progress (WIP). Se questa opzione è deselezionata, l'eliminazione non viene effettuata se sono presenti transazioni non stimate. 
   > [!NOTE]
   > Questa opzione è disponibile solo quando l'eliminazione viene applicata a un progetto stima. Non è disponibile se si utilizzano registrazioni periodiche. Questa impostazione funziona con le impostazioni della scheda **Stima** della pagina **Parametri progetto** nel gruppo di campi **Consenti eliminazione in presenza di transazioni non stimate**.
   - **Imposta fase su Finito**: abilitare questa opzione per impostare la fase del progetto stima su **Finito** dopo aver eseguito l'eliminazione.
   - **Stampa elenco stime**: selezionare le informazioni da includere nella stampa dell'elenco delle stime.
   - **Mostra Registro informazioni**: abilitare questa opzione per visualizzare il Registro informazioni.
   - **Data di registrazione**: scegliere la data di registrazione contabile della stima.

4.  Selezionare **OK**.
5. Al termine del processo di eliminazione, il progetto stima eliminato viene visualizzato con un valore negativo. 

Se una stima è stata eliminata per sbaglio, è possibile selezionare quella stima e quindi **Annulla eliminazione**.   
