---
title: Assegnazione e sostituzioni IVA
description: Questa procedura dimostra come assegnare fasce IVA ai canali di commercio.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74a7eed04648c63c0b19d5de26d2bdbef59aec7d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207598"
---
# <a name="sales-tax-assignment-and-overrides"></a>Assegnazione e sostituzioni IVA

[!include [banner](../../includes/banner.md)]

Questa procedura dimostra come assegnare fasce IVA ai canali di commercio. Inoltre illustra il processo di creare una nuova forzatura IVA e assegnarla ad un gruppo di forzatura IVA esistente. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Retail e Commerce > Canali > Punti vendita > Tutti i punti vendita.
2. Nella lista, fare clic sul collegamento ID canale per "Houston".
3. Fare clic su Modifica.
    * Il campo "Fascia IVA" contiene l'elenco di fasce IVA della società corrente. Il gruppo attualmente assegnato è una fascia IVA generica "Texas". Ci sono inoltre fasce IVA per "Washington" e "Washington, King County". Le fasce IVA possono includere imposte applicabili a più comuni.  
    * Il campo "Forzatura IVA" è dove i gruppi di forzatura IVA possono essere mappati al canale. I gruppi di forzatura IVA possono essere usati per raggruppare le forzature IVA che funzionano per più punti vendita. Piuttosto che manualmente assegnare le forzature IVA una per una, il gruppo può essere creato ed assegnato direttamente ai canali per risparmiare tempo.  
4. Fare clic su Salva.
5. Chiudere la pagina.
6. Passare a Retail e Commerce > Impostazione canale > IVA > Forzature IVA.
7. Fare clic su Nuovo.
8. Nel campo Forzatura IVA fornire un nome per la nuova forzatura.
9. Nel campo Descrizione immettere una descrizione della forzatura.
10. Impostare lo stato su "Abilitazione".
11. Espandere o comprimere la sezione Forzatura.
12. Selezionare un'opzione nel campo Tipo.
    * Le fasce IVA degli articoli possono essere usate per sostituire imposte per articoli specifici che appartengono alla fascia. Per esempio, i prodotti alimentari sono tassati tipicamente diversamente dai beni durevoli e hanno probabilmente la propria gascia IVA. Le fasce IVA sono gruppi di imposte che sono applicabili ad un canale particolare. Per esempio, se un canale vende sia al dettaglio che tra imprese, fasce IVA differenti possono essere usate. Tutte le imposte applicabili sarebbero mappate alla fascia IVA.  
    * Ora potete selezionare le imposte "Da" e "A" o "Da gruppo di imposta" e "A gruppo di imposta" per creare la forzatura IVA. Il campo "Da" indica l'imposta o il gruppo di imposta da forzare. La forzatura tramite fascia IVA degli articoli fornisce opzioni differenti dalla forzatura tramite fascia IVA. Le forzature IVA possono essere impostate per sostituire imposte su intere transazioni o su righe particolari nella transazione.  
13. Fare clic su Salva.
14. Chiudere la pagina.
15. Passare a Retail e Commerce > Impostazione canale > IVA > Gruppi di forzatura IVA.
    * In questo passaggio si assegnerà la forzatura IVA appena creata al gruppo di forzatura IVA assegnato al canale di Houston.  
16. Fare clic su Modifica.
17. Espandere o comprimere la sezione Impostazione.
18. Scegliere Aggiungi.
19. Nel campo Forzatura IVA fare clic sul pulsante a discesa per aprire la ricerca.
20. Selezionare la forzatura IVA precedentemente creata dall'elenco.
21. Nell'elenco fare clic sul collegamento nella riga selezionata.
22. Fare clic su Salva.

