---
title: Impostare un canale punto vendita online
description: Questo articolo fornisce informazioni sui canali di punti vendita online e su come impostarli in Dynamics 365 Commerce.
author: kfend
manager: AnnBe
ms.date: 03/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelManagementWorkspace, RetailOnlineStoreList
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b719e40720b091eec879edf332ab63db710a1ebc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096896"
---
# <a name="set-up-an-online-store-channel"></a>Impostare un canale punto vendita online

[!include [banner](includes/banner.md)]

Questo articolo fornisce informazioni sui canali di punti vendita online e su come impostarli in Dynamics 365 Commerce.

Commerce supporta più canali di vendita al dettaglio. Questi canali includono negozi online, call center e punti vendita al dettaglio, definiti anche punti vendita fisici. I negozi online offrono a un rivenditore una presenza online in modo che i clienti possano acquistare i prodotti anche tramite il punto vendita online, oltre che nei punti vendita fisici. I clienti che acquistano prodotti dal punto vendita online possono farseli spedire o prelevarli da un punto vendita locale. 

È possibile creare un punto vendita online nel client Commerce. Questo punto vendita online viene quindi pubblicato in un punto vendita online di terze parti che è integrato con Commerce. Il punto vendita online di terze parti serve come vetrina (interfaccia utente) per il punto vendita online e offre una scelta di funzionalità CMS (sistema di gestione clienti) e di interfaccia utente. Diverse integrazioni di questo tipo sono disponibili. 

Le proprietà definite per il punto vendita online determinano il comportamento del punto vendita online. Ad esempio, è possibile definire la gerarchia di categorie di navigazione e assegnarla al punto vendita online. Quando si pubblica il punto vendita online nel punto vendita online di terze parti, la gerarchia di categorie di navigazione viene visualizzata nella versione online del punto vendita. Gli acquirenti utilizzano la gerarchia di categorie di navigazione per esplorare il punto vendita online e per cercare i prodotti. 

Per creare un punto vendita online, è necessario impostare i componenti che consentono l'elaborazione delle transazioni per il punto vendita. Ad esempio, è necessario aggiungere assortimenti, applicare attributi e impostare metodi di pagamento e di spedizione. È inoltre possibile definire i prezzi, le promozioni, gli sconti, gli accordi commerciali e le condizioni di spedizione specifici del punto vendita online. 

Dopo aver pubblicato il punto vendita online nel punto vendita online di terze parti, è possibile creare cataloghi di prodotti per il punto vendita online. I prodotti del catalogo diventano elenchi di prodotti nel punto vendita online. Quando un acquirente acquista prodotti dal punto vendita online, le scorte disponibili vengono aggiornate e sincronizzate nel client. Inoltre, gli ordini cliente vengono generati per gli acquisti e inviati al client per l'esecuzione e l'elaborazione dell'ordine.

## <a name="set-up-an-online-store"></a>Impostare un punto vendita online

Per impostare un punto vendita online, è necessario completare le attività indicate di seguito.

1. Creare il punto vendita online.
2. Aggiungere il punto vendita online alle gerarchie organizzative appropriate.
3. Aggiungere gli assortimenti che includono i prodotti disponibili nel punto vendita online.
4. Assegnare o creare gruppi di prezzi per il punto vendita online.
5. Impostare le modalità di consegna disponibili per il punto vendita online.
6. Assegnare i metodi di pagamento che vengono accettati dal punto vendita online.
7. Se si consente agli acquirenti di ordinare i prodotti online e di prelevarli in un punto vendita locale, assegnare gruppi di localizzatori di punti vendita al punto vendita online.
8. Assegnare attributi per canali, prodotti e ordini cliente al punto vendita online. Gli attributi del canale si applicano all'intero punto vendita online, gli attributi del prodotto si applicano ai prodotti che vengono offerti nel punto vendita online e gli attributi degli ordini cliente si applicano agli ordini cliente generati dal punto vendita online.
9. Mappare gli attributi per definire le proprietà che determinano il comportamento degli attributi nel punto vendita online. Ad esempio, è possibile definire gli attributi come obbligatori o ricercabili.
10. Pubblicare il punto vendita online per generarne la struttura nel punto vendita online di terze parti di propria scelta.

    > [!IMPORTANT]
    > Prima di pubblicare il punto vendita online, è necessario impostare un percorso di distribuzione per lo stesso.

## <a name="commerce-channel-navigation-hierarchies"></a>Gerarchie di navigazione nei canali di commercio

Prima di creare un punto vendita online, è necessario definire la gerarchia di navigazione nei canali di commercio da utilizzare nel punto vendita. La gerarchia di navigazione nei canali rappresenta la gerarchia di categorie visualizzata nel punto vendita online dopo la pubblicazione del punto vendita. Quando si pubblicano cataloghi di prodotti nel punto vendita online, i prodotti presenti nel catalogo vengono mappati alle categorie della gerarchia di navigazione nei canali. Gli acquirenti usano quindi la gerarchia per esplorare il punto vendita online.

## <a name="organization-hierarchies"></a>Gerarchie organizzative

Le gerarchie organizzative sono utilizzate per strutturare canali di commercio e per rappresentare le relazioni tra le organizzazioni che fanno parte dell'azienda. Quando si impostano i negozi online, è possibile aggiungerli a una gerarchia organizzativa. I punti vendita, quindi, condividono i dati utilizzati per assortimenti, rifornimento e dichiarazione. 

Quando si crea una gerarchia organizzativa, è necessario assegnarle uno scopo. Lo scopo indica la modalità con cui viene utilizzata la gerarchia nella struttura aziendale. È possibile creare una gerarchia organizzativa per le operazioni del punto vendita e utilizzare tale gerarchia per assortimenti, rifornimento e reporting. 

In alternativa, è possibile creare una gerarchia organizzativa separata per ogni scopo. È inoltre possibile creare più gerarchie con lo stesso scopo e assegnare un canale separato a ognuna di esse. Se si intende pubblicare cataloghi di prodotti nel punto vendita online, è necessario almeno aggiungere il punto vendita online a una gerarchia organizzativa per gli assortimenti. I prodotti di un catalogo vengono selezionati dagli assortimenti assegnati al punto vendita online. Quando il catalogo viene pubblicato, il processo di pubblicazione confronta le date di validità per l'assortimento assegnato al punto vendita online ai prodotti inclusi nel catalogo per determinare i prodotti da rendere disponibili nel punto vendita online.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti di URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-B2C-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
