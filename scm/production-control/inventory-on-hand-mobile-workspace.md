---
title: Le disponibile l&quot;area di lavoro mobile per Microsoft Dynamics 365 per il app delle operazioni
description: Tramite mobili dell&quot;area di lavoro delle scorte disponibili effettuate le comprensioni spostati in magazzino disponibile e prenotato in qualsiasi momento e ovunque.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Le disponibile l'area di lavoro mobile per Microsoft Dynamics 365 per il app delle operazioni

Tramite mobili dell'area di lavoro delle scorte disponibili effettuate le comprensioni spostati in magazzino disponibile e prenotato in qualsiasi momento e ovunque. 

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                         | descrizione                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Letto di Microsoft Dynamics 365 per la presentazione di cellulare di operazioni | [Dynamics 365 per la presentazione mobile] di operazioni (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 per le operazioni                                          | In un ambiente con Microsoft Dynamics 365 per la versione 1611 delle operazioni e Microsoft Dynamics per l'aggiornamento 3 la piattaforma delle operazioni (novembre 2016) |
| 3215650 KB di Hotfix                                                    | Impostare il hotfix per abilitare le aree di lavoro che vengono fornite in Microsoft Dynamics 365 per le operazioni.                                       |
| Dispositivo mobile con Dynamics 365 per il app delle operazioni in | Scaricare Dynamics 365 per il app delle operazioni dalla memoria di cellulare del app.                                                                           |

## <a name="introduction"></a>Introduzione
In genere, le società con più spedizioni e più ricevimenti dell'inventario ogni giorno. Tali movimenti vengono modificati costantemente allo stato di disponibilità di magazzino. L'area di lavoro mobile per le scorte disponibili consente di visualizzare lo stato delle scorte interaziendali disponibili, in modo da poter ottenere le ultime comprensioni i dati del magazzino nel dispositivo mobile scelta. Indipendentemente dal fatto che si lavora nel magazzino, acquisto, di vendita, nella produzione, o nella gestione, o contengono altri ruoli, è possibile accedere a disposizione dei dati di magazzino in qualsiasi momento e ovunque. L'area di lavoro mobile offre un punto di vista istantaneo disponibile dello stato delle attrezzature e consente di visualizzare le scorte disponibili tra le attrezzature, le prenotazioni correnti materiali e le scorte disponibili non prenotato. È inoltre possibile immettere i numeri di articolo per eseguire query sulle scorte disponibili ed eseguire una ricerca filtrata disponibile per i prodotti o di varianti. In particolare, l'area di lavoro mobile sono disponibili le seguenti funzionalità:

-   È possibile cercare il numero o il nome prodotto sotto/co-prodotti per individuare i prodotti per visualizzare le scorte disponibili lo stato delle scorte.
-   Per i prodotti selezionati, è possibile visualizzare le seguenti informazioni:
    -   Scorte disponibili per sito
    -   Scorte disponibili per magazzino
    -   Scorte disponibili per l'ubicazione
    -   Scorte disponibili per batch (per i prodotti controllato per lotto)
    -   Scorte disponibili per stato di magazzino

<!-- -->

-   La quantità di prodotto disponibile viene visualizzato nei seguenti modi:
    -   Dall'inventario fisico (questa visualizzazione per l'importo totale.)
    -   Da quantità fisica prenotata (questa visualizzazione alla quantità prenotata).
    -   Dal valore Fisico disponibile (questa visualizzazione alla quantità disponibile per il quale non è necessario).

## <a name="get-started"></a>Per iniziare
Per iniziare sul dispositivo mobile:

1.  Dalla memoria di cellulare del app, download e impostare Microsoft Dynamics 365 per il app delle operazioni.
2.  Inizia app Approvazioni sull'unità.
3.  Immettere il proprio Dynamics 365 URL.
4.  Immettere la società in per accedere a. Ad esempio, immettere USMF ** **.
5.  La prima volta che ha in, verrà chiesto di specificare il nome utente e password per il sistema Microsoft Dynamics 365 per l'account operazioni. Immettere le credenziali. Dopo avere accesso in, vengono visualizzate le aree di lavoro disponibili per la società.

Per visualizzare le aree di lavoro nell'app Approvazioni di cellulare, è necessario rilasciare le aree di lavoro desiderate in Dynamics 365 per il app delle operazioni.

1.  Avviare Dynamics 365 per le operazioni.
2.  ** Fare clic su Amministrazione sistema ** &gt; ** l'impostazione ** &gt; ** parametri di sistema **.
3.  Selezionare ** gestire il app mobile **.
4.  Selezionare l'area di lavoro per emettere la piattaforma spostato.
5.  ** Pubblicare Selezionare l'area di lavoro **.
6.  Aggiorna la propria unità per visualizzare le aree di lavoro generati.

## <a name="view-the-onhand-inventory-for-a-product"></a>Visualizza il disponibile per un prodotto
1.  Nel dispositivo mobile, selezionare ** scorte disponibili ** l'area di lavoro.
2.  Selezionare ** controlli disponibili per un articolo **. Gli un elenco di prodotti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, 50 articoli vengono caricati, ma è possibile cambiare questo numero. Per ulteriori informazioni, vedere il manuale di preliminari read.
3.  Se all'articolo non è presente nell'elenco selezionare, cercare ** più ** effettuare una ricerca in linea in Dynamics 365 per le operazioni. Ricerca del numero di prodotti, o selezionare un nome di sottoprodotto di ricerca.
4.  Selezionare un prodotto. Se l'articolo è un'immagine, l'immagine verrà visualizzata.
5.  Selezionare una delle seguenti opzioni per visualizzare le scorte disponibili lo stato delle scorte:
    -   Visualizza le scorte disponibili per sito
    -   Visualizza le scorte disponibili per magazzino
    -   Visualizza le scorte disponibili per l'ubicazione
    -   Visualizza le scorte disponibili per batch (per i prodotti controllato per lotto)
    -   Visualizza le scorte disponibili per stato di magazzino

    La quantità di prodotto disponibile viene visualizzato nei seguenti modi:
    -   Dall'inventario fisico (questa visualizzazione per l'importo totale.)
    -   Da quantità fisica prenotata (questa visualizzazione alla quantità prenotata).
    -   Dal valore Fisico disponibile (questa visualizzazione alla quantità disponibile per il quale non è necessario).




