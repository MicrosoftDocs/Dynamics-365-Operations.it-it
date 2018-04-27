---
title: Stato del ciclo di vita prodotto
description: Uno stato del ciclo di vita del prodotto documenta lo stato del ciclo di vita di un prodotto rilasciato o di una variante di prodotto.
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: conradv
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 236b0253f20330f09f07dbcfa19257350fb5d37f
ms.openlocfilehash: 8ef72de3f226a3270ac0145a20e4da7dfe64f4ba
ms.contentlocale: it-it
ms.lasthandoff: 02/08/2018

---

# <a name="product-lifecycle-state"></a>Stato del ciclo di vita prodotto 

[!INCLUDE [banner](../includes/banner.md)]

Uno stato del ciclo di vita del prodotto documenta lo stato del ciclo di vita di un prodotto rilasciato o di una variante di prodotto. Gli stati del ciclo di vita del prodotto sono definiti dall'utente, in genere da responsabile di prodotto o un responsabile di dati master relativi alla rappresentazione generale prodotto. I processi aziendali specifici, ad esempio la pianificazione generale, possono essere interessati da uno stato specifico del ciclo di vita.   

Un prodotto rilasciato o una variante prodotto possono essere associati a uno stato del ciclo di vita del prodotto che documenta in quale stato del ciclo di vita si trova attualmente un prodotto o una variante specifici. È possibile definire qualsiasi numero di stati di ciclo di vita del prodotto assegnando un nome e una descrizione allo stato. È possibile selezionare uno stato del ciclo di vita come stato predefinito per i nuovi prodotti rilasciati. Le varianti prodotto rilasciate ereditano il relativo stato del ciclo di vita del prodotto in base alla rappresentazione generale prodotto rilasciato alla creazione. Quando si modifica lo stato del ciclo di vita in una rappresentazione generale prodotto rilasciato, è possibile scegliere di aggiornare tutte le varianti esistenti con lo stesso stato originale.  

## <a name="create-a-new-product-lifecycle-state"></a>Creare un nuovo stato del ciclo di vita prodotto 

- Per creare un nuovo stato del ciclo di vita del prodotto, riprodurre o leggere la guida attività **Creare un nuovo stato del ciclo di vita prodotto**. 

-  Per creare uno stato predefinito del ciclo di vita del prodotto, riprodurre o leggere la guida attività **Creare uno stato predefinito del ciclo di vita prodotto**.   

## <a name="associate-product-lifecycle-states-to-released-products"></a>Associare gli stati del ciclo di vita del prodotto ai prodotti rilasciati  

Esistono vari modi per associare uno stato del ciclo di vita del prodotto ai prodotti rilasciati o a varianti prodotto.

-  Nella creazione di un nuovo prodotto rilasciato, il valore predefinito **Stato del ciclo di vita prodotto** viene assegnato automaticamente. 
-  Nel rilascio di un prodotto in una persona giuridica, il valore predefinito **Stato del ciclo di vita prodotto** viene assegnato automaticamente. 
-  Nel rilascio di una variante prodotto a una persona giuridica, lo **Stato del ciclo di vita prodotto** associato alla rappresentazione generale prodotto rilasciato nella persona giuridica viene assegnato automaticamente alla nuova variante. 

È possibile aggiornare manualmente lo stato del ciclo di vita del prodotto tramite: 

-    La pagina elenco **Prodotti rilasciati** o **Visualizzazione dettagli**. 
-  La pagina elenco **Varianti prodotti rilasciati** o **Visualizzazione dettagli**. 
-  Trovare i prodotti o le varianti prodotto obsoleti in base alla richiesta e associare uno stato del ciclo di vita.  

Per informazioni dettagliate su come associare gli stati del ciclo di vita del prodotto, leggere o riprodurre le due seguenti guide attività.

-  Per associare uno stato del ciclo di vita di prodotto a una rappresentazione generale prodotto rilasciato, leggere o riprodurre la guida **Assegnare uno stato del ciclo di vita prodotto a una rappresentazione generale prodotto rilasciato**. 

-  Per associare uno stato del ciclo di vita di prodotto a un prodotto di rilascio, leggere o riprodurre la guida **Assegnare uno stato del ciclo di vita prodotto a un prodotto rilasciato**. 

## <a name="impact-on-master-planning"></a>Impatto sulla pianificazione generale 

Lo stato del ciclo di vita del prodotto dispone solo di un flag di controllo: **Attivo per pianificazione**. Per impostazione predefinita, è impostato su **Sì** per tutti gli stati creati per ciclo di vita del prodotto, ma può essere modificato come **No**. Quando l'opzione impostata è **No**, i prodotti rilasciati o le varianti prodotto rilasciati sono: 

-  Escluso dalla pianificazione generale. 
-  Escluso dal calcolo del livello DBA. 

Per informazioni dettagliate su come utilizzare lo stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione generale e dal calcolo del livello BOM, riprodurre o leggere la guida attività **Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale**.

> [!NOTE]
> Per motivi di prestazioni, si consiglia vivamente di associare tutti i prodotti o le varianti di prodotto rilasciati obsoleti, specialmente quando si lavora con varianti di configurazione del prodotto non riutilizzabili, con uno stato del ciclo di vita del prodotto che è disattivato per la pianificazione generale.  

## <a name="default-migration-import-and-export"></a>Migrazione, importazione ed esportazione predefinite 

Gli stati del ciclo di vita del prodotto non sono supportati da entità di dati e lo stato del ciclo di vita non può essere impostato su uno stato variabile tramite le entità di dati del prodotto rilasciato.

-  Nella migrazione dalle versioni precedenti, lo stato del ciclo di vita di tutti i prodotti e le varianti prodotto risulterà vuoto.  
-  Quando si importano prodotti rilasciati attraverso un'entità di dati, lo stato del ciclo di vita predefinito verrà applicato alla creazione.  
-  Quando si importano varianti di prodotto rilasciate tramite un'entità di dati, viene importato lo stato del ciclo di vita del prodotto della rappresentazione generale prodotto rilasciato.   

## <a name="find-obsolete-products-and-products-variants"></a>Trovare prodotti e varianti prodotto obsoleti 

È possibile eseguire un'analisi di simulazione per individuare i prodotti o le varianti prodotto rilasciati obsoleti quindi aggiornare lo stato del ciclo di vita del prodotto. Per trovare i prodotti obsoleti, riprodurre e leggere la guida attività **Trovare i prodotti o le varianti prodotto obsoleti in base alla richiesta e associare uno stato del ciclo di vita**. Questa guida attività mostra come trovare prodotti o varianti di prodotto obsoleti e come associare uno stato del ciclo di vita del prodotto ai prodotti obsoleti. Inoltre mostra come visualizzare i risultati della simulazione e valutare quanti prodotti e varianti di prodotto saranno associati a un nuovo stato del ciclo di vita del prodotto quando si esegue l'aggiornamento senza simulazione.  

Tramite l'esecuzione dell'analisi in una modalità di simulazione, prodotti e varianti prodotto identificati come obsoleti vengono visualizzati in un modulo specifico, in cui possono essere esaminati facilmente. L'analisi effettua la ricerca di transazioni e dati master specifici per identificare i prodotti privi di richiesta durante un periodo variabile e senza dati master che possono determinare la domanda. I nuovi prodotti rilasciati durante un periodo variabile possono essere esclusi dall'analisi. Quando la simulazione di analisi restituisce il risultato previsto, l'utente può eseguire l'analisi e impostare un nuovo stato del ciclo di vita di prodotti per tutti i prodotti identificati come obsoleti dall'analisi.  

> [!NOTE]
> Tenere presente che tutte le analisi e tutti gli aggiornamenti devono essere effettuati all'interno della stessa persona giuridica.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Criteri per selezionare e aggiornare prodotti o varianti di prodotto rilasciati 

Usare i seguenti criteri per selezionare e aggiornare i prodotti o le varianti di prodotto rilasciati: 

-    Lo stato del ciclo di vita del prodotto o della variante del prodotto deve essere diverso dal nuovo stato desiderato. 
-  Il prodotto o la variante prodotto è stata creata alcuni giorni fa in base al numero di giorni immessi nella finestra di dialogo per la selezione. 
-  Non sono presenti ordini di produzione aperti (= stato < finito) per prodotto o variante prodotto. 
-  Non sono presenti transazioni di magazzino aperte (= stato rilascio da ReservPhysical a QuotationIssue o stato entrata da Registrered a QuotationReceipt) per prodotto o variante prodotto. 
-  Non sono presenti transazioni di magazzino all'interno dell'ultimo numero di giorni per il prodotto o la variante prodotto. 
-  Non esiste alcuna richiesta o futura previsione dell'offerta per il prodotto o la variante prodotto.  
-  Nessun livello scorte minime è stato impostato nella copertura dell'articolo per il prodotto o la variante prodotto. 
-  Nessuna regola kanban a quantità fissa attiva per il prodotto o la variante prodotto.  
-  Nessuna riga ordine di assistenza per il prodotto o la variante prodotto. 
-  Nessun vendita o contratto di acquisto attive o future righe per il prodotto o la variante prodotto. 
-  Il prodotto o la variante prodotto non sono utilizzati in una DBA associata a una versione DBA approvata non scaduta per un prodotto o una variante attiva per la pianificazione.

## <a name="related-topics"></a>Argomenti correlati

-  [Creare uno stato del ciclo di vita di prodotto (guida attività)](tasks/new-product-lifecycle-state.md)
-  [Creare uno stato del ciclo di vita di prodotto predfinito (guida attività)](tasks/default-product-lifecycle-state.md)
-  [Assegnare uno stato del ciclo di vita di prodotto a una rappresentazione generale prodotto rilasciato (guida attività)](tasks/product-lifecycle-state-released-product-master.md)
-  [Assegnare uno stato del ciclo di vita di prodotto a un prodotto rilasciato (guida attività)](tasks/product-lifecycle-state-released-product.md)
-  [Trovare i prodotti o le varianti prodotto obsoleti e associare uno stato del ciclo di vita (guida attività)](tasks/obsolete-product-variants.md)
-  [Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale (guida attività)](tasks/exclude-products-master-planning.md)

