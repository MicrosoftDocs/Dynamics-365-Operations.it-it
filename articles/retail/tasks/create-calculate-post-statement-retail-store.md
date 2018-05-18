--- 
title: " Creare, calcolare e registrare un rendiconto per un punto vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 33ebb28196baa9ae944dbd124274b05cb587fea4
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a> Creare, calcolare e registrare un rendiconto per un punto vendita al dettaglio

[!include [task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita. Sono disponibili altri processi batch che è possibile configurare per le stesse attività. I passaggi per la configurazione e l'esecuzione dei processi batch sono presenti in altri argomenti. Per completare questa procedura, è necessario disporre delle transazioni che sono state completate nel POS e sottoposte al pull in Dynamics AX. Questa registrazione utilizza i dati dimostrativi della società USRT. Questa procedura può fare riferimento a Microsoft Dynamics AX. Notare che Dynamics AX è ora denominato Microsoft Dynamics 365 for Operations.

1. Passare a Tutte le aree di lavoro  > Dati finanziari punto vendita al dettaglio.
2. Fare clic su Nuovo rendiconto.
3. Nel campo Numero punto vendita fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic su OK.
    * Il gruppo di impostazione dispone delle impostazioni che controllano quali transazioni vengono incluse nel rendiconto e come vengono raggruppate le linee del rendiconto. È possibile aprire il gruppo di impostazione e modificare queste impostazioni oppure utilizzare le impostazioni predefinite.  
    * Il campo Metodo rendiconto determina come le linee del rendiconto vengono raggruppate.  
    * Selezionare i membri del personale o un registratore di cassa se si desidera calcolare un rendiconto solo per un registratore o un membro del personale specifico.  
6. Selezionare un'opzione nel campo Metodo di chiusura.
7. Fare clic su Calcola rendiconto.
8. Fare clic su Sì.
    * Dopo il calcolo del rendiconto, è necessario creare le righe con gli importi totali per ciascun metodo di pagamento e metodo di rendiconto utilizzato.  
    * Immettere un importo conteggiato in ogni riga se è necessario immetterlo o aggiornarlo. Il campo conteggiato viene popolato con gli importi dei riepiloghi incassi eseguiti nel POS.  
9. Fare clic su Registra rendiconto.
10. Fare clic su Chiudi.
11. Andare a Vendita al dettaglio e commercio > Canali > Dati finanziari punto vendita al dettaglio.
12. Fare clic sulla scheda Rendiconti registrati.


