---
title: Impostare un modello di configurazione prodotto
description: Questo articolo descrive i passaggi per l&quot;impostazione e la creazione di un modello di configurazione prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8307ad3be2bc2799abdf057123b6022c7032b191
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-a-product-configuration-model"></a>Impostare un modello di configurazione prodotto

[!include[banner](../includes/banner.md)]


Questo articolo descrive i passaggi per l'impostazione e la creazione di un modello di configurazione prodotto.

| Compito                                                        | descrizione                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Creare una rappresentazione generale prodotto.                                    | Creare una rappresentazione generale prodotto nell'elenco **Rappresentazione generale prodotto**. Rilasciare la rappresentazione generale prodotto a tutte le società pertinenti. Per una rappresentazione generale prodotto utilizzata come versione per un modello di configurazione prodotto o come sottocomponente, l'opzione **Configurazione basata su vincoli** deve essere selezionata come tecnologia di configurazione e la dimensione di configurazione deve essere selezionata solo per il gruppo di dimensioni prodotto. |
| Creare componenti.                                          | Creare i componenti nella pagina **Componenti**. I componenti sono i blocchi predefiniti di un modello di configurazione prodotto e possono essere riutilizzati in più modelli di configurazione prodotto.                                                                                                                                                                                                                      |
| Creare tipi di attributo.                                     | Creare i tipi di attributo nella pagina **Tipi di attributo**. I tipi di attributo specificano i tipi di set di dati per gli attributi utilizzati nei modelli di configurazione prodotto. Gli attributi di tipo **Booleano**, **Testo** con un elenco fisso e **Intero** con tipi di intervallo elencano il set di valori disponibili quando si configura una variante prodotto in base a un modello di configurazione prodotto.       |
| .Creare un modello di configurazione prodotto                       | Creare un modello di configurazione prodotto nella pagina **Nuovo modello di configurazione prodotto**.                                                                                                                                                                                                                                                                                                              |
| Aggiungere attributi a un modello di configurazione prodotto.            | Creare un attributo nella scheda dettaglio **Attributi** nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**. Gli attributi descrivono tutte le funzionalità del modello di configurazione prodotto.                                                                                                                                                                                                       |
| Aggiungere vincoli a un modello di configurazione prodotto.           | Creare vincoli nella scheda dettaglio **Vincoli** nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**. I vincoli sono limitazioni che una configurazione prodotto deve soddisfare. e si distinguono in vincoli di espressione e vincoli di tabella.                                                                                                                                 |
| Aggiungere sottocomponenti a un modello di configurazione dei prodotti.         | Creare sottocomponenti nella scheda dettaglio **Sottocomponenti** nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**. I sottocomponenti sono correlati ai componenti e sono collegati agli articoli che rappresentano il sottocomponente.                                                                                                                                                                       |
| Aggiungere requisiti utente a un modello di configurazione prodotto.     | I requisiti degli utenti sono simili a sottocomponenti, ma non fanno riferimento a un articolo. È possibile pensare a requisiti utente come DBA fittizia. Tutte le righe DBA o tutte operazioni del ciclo di lavorazione che sono posizionate direttamente nell'ambito dei requisiti utente verranno compresse nel componente principale.                                                                                                                       |
| Aggiungere righe DBA a un modello di configurazione prodotto.             | Creare righe DBA nella scheda dettaglio **Righe DBA** nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**. Le righe DBA rappresentano una parte necessaria per generare una variante del prodotto.                                                                                                                                                                                                 |
| Aggiungere operazioni del ciclo di lavorazione a un modello di configurazione prodotto.      | Creare operazioni del ciclo di lavorazione nella scheda dettaglio **Operazioni ciclo di lavorazione** nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**. Le operazioni del ciclo di lavorazione rappresentano un passaggio in una sequenza di passaggi eseguiti per creare una variante del prodotto.                                                                                                                                                    |
| Creare una versione attiva di un modello di configurazione prodotto. | Creare una versione attiva del modello di configurazione prodotto nella pagina **Versioni**. Una versione è la relazione tra un modello di configurazione prodotto e una rappresentazione generale prodotto. Un modello di configurazione prodotto con una versione attiva può essere configurato da un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.                                                               |
| Testare un modello di configurazione prodotto.                         | Testare il modello di configurazione del prodotto nella pagina **Dettagli modello di configurazione prodotto basato su vincoli** o nella pagina elenco **Modello di configurazione prodotto**. Il test dei modelli di configurazione prodotto simula il processo di configurazione del modello prodotto che si verifica durante la gestione degli ordini.                                                                                                |
| Creare un modello di configurazione prodotto.                | Creare un modello di configurazione prodotto nella pagina **Modelli di configurazione**. Un modello di configurazione include i valori degli attributi nel modello di configurazione prodotto. Selezionare i valori di attributo nella pagina **Configura riga**. È possibile scegliere di caricare un modello di configurazione del modello prodotto durante la configurazione del modello prodotto.                                                   |
| Configurare un articolo.                                          | I modelli di configurazione prodotto possono essere configurati da un ordine cliente, un'offerta di vendita, un ordine fornitore o un ordine di produzione.                                                                                                                                                                                                                                                                           |






