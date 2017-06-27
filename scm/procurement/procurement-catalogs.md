---
title: Cataloghi di approvvigionamento
description: "Questo articolo descrive, in modo generale, in che modo i professionisti degli acquisti possono impostare e gestire i cataloghi di approvvigionamento. I cataloghi di approvvigionamento definiscono gli articoli e i servizi che i dipendenti della società possono ordinare per uso interno."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 15767a54da25c293bb3d6d5e0a14e7e05a7d730b
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="procurement-catalogs"></a>Cataloghi di approvvigionamento

[!include[banner](../includes/banner.md)]


Questo articolo descrive, in modo generale, in che modo i professionisti degli acquisti possono impostare e gestire i cataloghi di approvvigionamento. I cataloghi di approvvigionamento definiscono gli articoli e i servizi che i dipendenti della società possono ordinare per uso interno.

I professionisti degli acquisti possono creare e gestire cataloghi degli articoli e dei servizi che possono essere acquistati per uso interno in un'organizzazione. Dopo che i cataloghi vengono impostati, i dipendenti della società possono creare richieste di acquisto per ordinare tramite essi. I cataloghi possono essere utilizzati per applicare i criteri di acquisto, in modo che i dipendenti possano ordinare solo gli articoli e i servizi autorizzati per la loro persona giuridica acquirente. Quando si crea un catalogo di approvvigionamento, è necessario considerare le seguenti attività:

-   Configurare la gerarchia di categorie di approvvigionamento prima di creare il catalogo.
-   Stabilire quali prodotti si desidera che i dipendenti possono ordinare. È possibile visualizzare o nascondere prodotti specifici in un nodo del catalogo o è possibile nascondere o visualizzare tutti i prodotti in un nodo.
-   Stabilire di quanti cataloghi di approvvigionamento si ha bisogno. L'accesso a un catalogo di approvvigionamento è determinato dalla regola dei criteri del catalogo che viene configurata per la persona giuridica e l'unità operativa cui è assegnato un dipendente.

Diversi fattori determinano i prodotti che i dipendenti possono ordinare e le categorie di approvvigionamento che possono utilizzare quando creano richieste di acquisto:

-   La regola dei criteri di accesso alle categorie nei criteri di acquisto determina quali categorie di approvvigionamento sono disponibili nella richiesta di acquisto. Se non è definita alcuna regola, tutte le categorie di approvvigionamento sono disponibili.
-   I dipendenti possono ordinare un prodotto solo se si trova nel catalogo di approvvigionamento attivo per l'organizzazione e in un nodo attivato e non nascosto. Il prodotto deve essere in una categoria cui un dipendente specifico può accedere in base alla regola dei criteri di accesso alle categorie.
-   La regola dei criteri di catalogo determina il catalogo utilizzato. Se non si definisce alcuna regola dei criteri di catalogo, la regola di accesso alle categorie da sola determina i prodotti che un dipendente può ordinare inviando la richiesta.

## <a name="prerequisites"></a>Prerequisiti
La tabella seguente descrive le attività che è necessario eseguire prima che un professionista degli acquisti possa creare un catalogo di approvvigionamento.

| Attività                                                | Ruolo               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Impostare una gerarchia di categorie di approvvigionamento.            | Responsabile acquisti | Le gerarchie di categorie di approvvigionamento classificano gli articoli o le transazioni per i report e l'analisi. Utilizzando una gerarchia di categorie di approvvigionamento, le società possono gestire in modo strategico categorie, prodotti, fornitori e altri fattori di approvvigionamento centralmente. Una gerarchia di categorie di approvvigionamento viene definita per un'intera organizzazione. Il catalogo si basa sulla gerarchia di categorie di approvvigionamento: le categorie della gerarchia diventano nodi del catalogo. I fornitori e i prodotti sono inclusi nel catalogo. |
| Aggiungere fornitori e prodotti alle categorie di approvvigionamento. | Responsabile acquisti | Quando viene creata la gerarchia di categorie di approvvigionamento per l'organizzazione, ciascuna categoria di approvvigionamento può essere associata a specifici fornitori, prodotti e così via. Queste associazioni vengono copiate automaticamente nel catalogo.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Impostazione di un catalogo
Dopo aver soddisfatto i prerequisiti, è possibile impostare cataloghi. È possibile creare un catalogo utilizzato dall'intera organizzazione o più cataloghi utilizzati dalle varie divisioni dell'organizzazione. Se si crea un catalogo per l'intera organizzazione, l'accesso al catalogo è controllato dalle regole dei criteri di acquisto.  

Il catalogo definisce quali prodotti sono disponibili quando le richieste di acquisto vengono create, ma è possibile utilizzare le regole dei criteri di accesso alle categorie per applicare restrizioni aggiuntive. Poiché i nodi di un catalogo sono categorie di approvvigionamento, possono essere eliminati da una regola dei criteri di accesso alle categorie. In questo caso, i prodotti nella categoria non sono disponibili per i dipendenti da utilizzare nelle richieste. Si definiscono le regole dei criteri di accesso alle categorie nella pagina **Criteri acquisto**. Nella seguente tabella vengono descritte le attività che è necessario eseguire per impostare un catalogo.

| Attività                                                   | Ruolo             | Descrizione                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consente di creare un nuovo catalogo.                                  | Addetto acquisti | Quando si crea un catalogo, si specifica un nome e una descrizione. Si stabilisce, inoltre, se il catalogo viene aggiornato manualmente o in automatico e si specifica il proprietario del catalogo.                                                                                                                                      |
| Controllare se i prodotti sono disponibili nel catalogo. | Addetto acquisti | Poiché i prodotti vengono ereditati dalle categorie di approvvigionamento, vengono tutti visualizzati nei nodi appropriati del catalogo. È possibile verificare se tutti i prodotti di un nodo sono nascosti o visualizzati quando il catalogo viene utilizzato in una richiesta di acquisto. È inoltre possibile verificare se i singoli prodotti di un nodo sono nascosti o visualizzati. |
| Pubblicare il catalogo.                                   | Addetto acquisti | Prima che un catalogo sia disponibile per essere utilizzato dai dipendenti in una richiesta, è necessario definire una regola dei criteri del catalogo, impostare lo stato del catalogo su **Attivo** e pubblicare il catalogo. È inoltre possibile disattivare i cataloghi che non si desidera più rendere disponibili agli utenti.                                              |

Gli aggiornamenti vengono pubblicati automaticamente o manualmente, a seconda dell'opzione selezionata per il catalogo nel campo **Tipo di aggiornamento predefinito** della pagina **Cataloghi**. Per i cataloghi sono disponibili i seguenti tipi di aggiornamento predefiniti:

-   **Dinamico**: il catalogo viene aggiornato automaticamente ogni volta che viene modificato.
-   **Statico**: i cataloghi devono essere aggiornati manualmente.
-   **Entrambi**: se il catalogo include categorie di prodotti con un tipo di aggiornamento predefinito **Statico**, deve essere aggiornato manualmente quando vengono aggiornate queste categorie. Se il catalogo include categorie di prodotti con un aggiornamento predefinito di tipo **Dinamico**, viene aggiornato automaticamente ogni volta che viene modificato.


<a name="see-also"></a>Vedere anche
--------

[Impostare una gerarchia di categorie di approvvigionamento (guida attività)](http://ax.help.dynamics.com/en/wiki/set-up-a-procurement-category-hierarchy/)




