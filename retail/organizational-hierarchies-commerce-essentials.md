---
title: Organizzazioni e gerarchie organizzative (elementi fondamentali del commercio)
description: "Elementi fondamentali del commercio ha tre tipi di organizzazioni interne che è possibile definire per consentire a un&quot;organizzazione per svolgere un processo aziendale o raggiungere un obiettivo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 93711977ad8d861ca75ba80ee542ee112c8ddd2f
ms.lasthandoff: 03/31/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organizzazioni e gerarchie organizzative (elementi fondamentali del commercio)

Elementi fondamentali del commercio ha tre tipi di organizzazioni interne che è possibile definire per consentire a un'organizzazione per svolgere un processo aziendale o raggiungere un obiettivo. 

Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o per raggiungere un obiettivo. Una gerarchia organizzativa rappresenta le relazioni tra le Business Unit che fanno parte dell'organizzazione.

## <a name="organizations"></a>Organizzazioni
In Elementi fondamentali del commercio è possibile definire tre tipi di organizzazioni interne: persone giuridiche, unità operative e team. In Microsoft Dynamics AX, tutte le organizzazioni interne sono tipi dell'entità Parte. Di conseguenza, utilizzano le funzionalità della rubrica per archiviare indirizzi e altre informazioni sul contatto. Una parte, che può essere una persona o un'organizzazione, può appartenere a una o più rubriche.
### <a name="legal-entities"></a>Persone giuridiche

Una persona giuridica è un'organizzazione dotata di una struttura legale istituita o registrata. Le persone giuridiche possono stipulare contratti e hanno l'obbligo di preparare rendiconti sul loro rendimento. Una società è un tipo di persona giuridica in Microsoft Dynamics AX, ogni persona giuridica è associata a un ID società. Questa associazione esiste perché un ID società, o DataAreaId, viene utilizzato in alcuni modelli di dati in cui le società vengono utilizzate come limite di protezione dei dati. Gli utenti possono accedere solo ai dati della società a cui sono collegati.

### <a name="operating-units"></a>Unità operative

Un'unità operativa è un'organizzazione utilizzata per dividere il controllo delle risorse economiche e dei processi operativi in un'azienda. Le persone in un'unità operativa hanno il compito di ottimizzare l'utilizzo delle risorse meno efficienti, di migliorare i processi e di rendere conto delle loro prestazioni. In Elementi fondamentali del commercio i tipi di unità operative includono centri di costo, business unit, flussi del valore, reparti e canali di vendita al dettaglio. Nella tabella riportata di seguito vengono fornite ulteriori informazioni su ciascun tipo di unità operativa.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo di unità operativa** | **Descrizione**                                                                         | **Scopo**                                                                                                                                 |
| Business Unit           | Unità operativa semi-autonoma creata per conseguire gli obiettivi aziendali strategici. | Le Business Unit vengono utilizzate per il reporting finanziario basato su settori o linee di prodotti che l'organizzazione serve nelle persone giuridiche. |
| Canale di vendita al dettaglio          | Un'unità operativa che rappresenta un punto vendita fisico.                             | Può essere utilizzato per gestire e controllare uno o più punti vendita all'interno di una o più persone giuridiche.                                                               |

## <a name="organizational-hierarchies"></a>Gerarchie organizzative
In Elementi fondamentali del commercio, a ogni gerarchia viene assegnato uno scopo. Lo scopo di una gerarchia determina i tipi di organizzazioni che è possibile includere nella gerarchia. Lo scopo consente inoltre di determinare gli scenari di applicazione per la gerarchia. Ad esempio, una gerarchia punti vendita al dettaglio può essere utilizzata per acquistare e vendita di prodotti in una vendita al dettaglio. Le organizzazioni di una gerarchia possono condividere parametri, criteri e transazioni. Le organizzazioni possono ereditare o sostituire i parametri della relativa organizzazione padre. Tuttavia, l'anagrafica condivisa, ad esempio prodotti e rubriche, vengono applicati a tutta l'organizzazione e non possono essere sostituiti per le singole organizzazioni.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Procedure consigliate per l'impostazione di un'organizzazione in una gerarchia

Quando si implementa una gerarchia organizzativa, considerare le procedure ottimali seguenti:
-   Creare un reparto per specificare l'intersezione tra una persona giuridica e una Business Unit. È quindi possibile riepilogare i dati da un reparto a una persona giuridica per una dichiarazione statutaria e da un reparto a una Business Unit per la creazione di report interni.
-   In una singola persona giuridica, non impostare più gerarchie per lo stesso scopo di gerarchia.
-   Non creare una gerarchia per ogni scopo. In genere, è possibile utilizzare una gerarchia per più scopi. Ad esempio, una gerarchia di unità operative può essere assegnata a tutti gli scopi correlati ai criteri.
-   Creare gerarchie bilanciate. In una gerarchia tutti i nodi che si trovano alla stessa distanza dal nodo radice sono definiti livelli. In una gerarchia bilanciata a ogni livello può trovarsi solo un tipo di unità operativa e la distanza dal nodo radice a ogni livello è coerente. Se esistono livelli intermedi tra un reparto e una persona giuridica o una Business Unit, potrebbero essere necessarie delle organizzazioni segnaposto per creare una gerarchia bilanciata.
-   Non impostare una gerarchia separata di unità operative se la struttura per le persone giuridiche è anche la struttura operativa. Una gerarchia mista di persone giuridiche e unità operative può servire a entrambi gli scopi.
-   Prima di impostare strutture di ristrutturazione consistenti, utilizzare le date di validità della gerarchia per effettuare un'analisi dell'impatto e un test di convalida.
-   Salvare una gerarchia come bozza se è necessario modificare una gerarchia prima della pubblicazione.
-   Limitare il numero di persone che dispongono delle autorizzazioni per aggiungere o rimuovere organizzazioni da una gerarchia in un ambiente di produzione. Un numero inferiore riduce le possibilità di commettere costosi errori.

## <a name="retail-store-management"></a>Gestione punto vendita al dettaglio
Nella seguente tabella sono descritti gli scenari di Elementi fondamentali del commercio in cui le gerarchie organizzative possono essere utilizzate.
| Attività                                                                           | Descrizione                                                                                                                                                                                                                                                                                                | Scopo gerarchia    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Gestire l'assortimento di articoli al dettaglio                                                      | Identificare i prodotti che sono disponibili in ciascun punto vendita al dettaglio.                                                                                                                                                                                                                                             | Assortimento di articoli al dettaglio    |
| Gestire il rifornimento per la vendita al dettaglio                                                    | Raggruppare i negozi per rifornire le scorte in base alle regole di rifornimento.                                                                                                                                                                                                                                          | Rifornimento per vendita al dettaglio |
| Creare report di dati per i negozi                                                         | Raggruppare i negozi per la creazione dei report.                                                                                                                                                                                                                                                                                | Report per vendita al dettaglio     |
| Registrare il magazzino, calcolare o registrare i rendiconti per un gruppo di negozi | Creare un gruppo di negozi che possa essere assegnato a un processo batch. Quando si definisce un processo batch per la registrazione del magazzino, il calcolo o la registrazione dei rendiconti, è possibile specificare a quale gerarchia applicare il processo. Quando si aggiungono o si rimuovono i negozi dalla gerarchia, non è necessario modificare il processo batch. | Registrazione Retail POS   |




