---
title: Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio
description: In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4517b9ddeb648b3d789773fc0dcb1ecd3c8be85c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024800"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a>Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita. Sono disponibili altri processi batch che è possibile configurare per le stesse attività. I passaggi per la configurazione e l'esecuzione dei processi batch sono presenti in altri argomenti. Per completare questa procedura, è necessario disporre delle transazioni che sono state completate nel POS e sottoposte al pull in Dynamics 365 Retail. Questa registrazione utilizza i dati dimostrativi della società USRT.

1. Selezionare **Dati finanziari punto vendita al dettaglio** da home page.
2. Selezionare **Nuovo rendiconto**.
3. Nel campo **Numero punto vendita**, selezionare un'opzione dall'elenco a discesa.
4. Selezionare **OK**.
5. Il gruppo di **impostazione** dispone delle impostazioni che controllano quali transazioni vengono incluse nel rendiconto e come vengono raggruppate nelle righe del rendiconto. È possibile aprire il gruppo di **impostazione** e modificare queste impostazioni oppure utilizzare le impostazioni predefinite.  
    - Il campo **Metodo rendiconto** determina come le righe del rendiconto vengono raggruppate.  
    - Selezionare un membro del personale o un registratore di cassa nel campo **Personale/registratore di cassa** se si desidera calcolare un rendiconto solo per un registratore o un membro del personale specifico.  
6. Selezionare un'opzione nel campo **Metodo di chiusura**.
7. Selezionare **Calcola rendiconto** nel riquadro azioni.
8. Selezionare **Sì**.
    - Dopo il calcolo del rendiconto, è necessario creare le righe con gli importi totali per ciascun metodo di pagamento e metodo di rendiconto utilizzato.  
    - Immettere un importo conteggiato in ogni riga se è necessario immetterlo o aggiornarlo. Il campo conteggiato viene popolato con gli importi dei riepiloghi incassi eseguiti nel POS.  
9. Selezionare **Registra rendiconto** nel riquadro azioni.
10. Selezionare **Chiudi**.
11. Chiudere il riquadro.
12. Nella home page selezionare **Dati finanziari punto vendita al dettaglio**.
13. Fare clic sulla scheda **Rendiconti registrati**.

