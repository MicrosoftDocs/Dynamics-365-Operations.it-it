---
title: Organizzazioni e gerarchie organizzative
description: Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o raggiungere un obiettivo. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72834769e393382ac511ad3af21544efddb049d3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545835"
---
# <a name="organizations-and-organizational-hierarchies"></a>Organizzazioni e gerarchie organizzative

[!include [banner](../includes/banner.md)]

Un'organizzazione è un gruppo di persone che collaborano per svolgere un processo aziendale o raggiungere un obiettivo. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda.

## <a name="organizations"></a>Organizzazioni

In Microsoft Dynamics 365 for Finance and Operations è possibile definire i seguenti tipi di organizzazioni interne: persone giuridiche, unità operative e team.

Tutte le organizzazioni interne sono tipi di entità di **Parte**. Di conseguenza, utilizzano le funzionalità della rubrica per archiviare l'indirizzo e le informazioni sul contatto. Una parte, che può essere una persona o un'organizzazione, può appartenere a una o più rubriche.

### <a name="legal-entities"></a>Persone giuridiche

Una persona giuridica è un'organizzazione dotata di una struttura legale istituita o registrata. Le persone giuridiche possono stipulare contratti e hanno l'obbligo di preparare rendiconti sul loro rendimento.

Una società è un tipo di persona giuridica. In questa versione di Microsoft Dynamics 365 for Finance and Operations, le società sono l'unico tipo di persona giuridica che è possibile creare e ogni persona giuridica è associata a un ID società. Questa associazione esiste perché alcune aree funzionali del programma utilizzano un ID società, o DataAreaId, nei loro modelli di dati. In queste aree funzionali, le società vengono usate come limite per la sicurezza dei dati. Gli utenti possono accedere solo ai dati della società a cui sono collegati.

### <a name="operating-units"></a>Unità operative

Un'unità operativa è un'organizzazione utilizzata per dividere il controllo delle risorse economiche e dei processi operativi in un'azienda. Le persone in un'unità operativa hanno il compito di ottimizzare l'utilizzo delle risorse meno efficienti, di migliorare i processi e di rendere conto delle loro prestazioni.

In Microsoft Dynamics 365 for Finance and Operations i tipi di unità operative includono centri di costo, business unit, flussi del valore, reparti e canali di vendita al dettaglio. Nella tabella riportata di seguito vengono fornite ulteriori informazioni su ciascun tipo di unità operativa.

| Tipo di unità operativa | Descrizione | Scopo |
|---------------------|-------------|---------|
| Centro di costo         | Unità operativa i cui manager sono responsabili delle spese a budget ed effettive. | Serve per la gestione e il controllo operativo di processi aziendali che si estendono a più persone giuridiche. |
| Business Unit       | Unità operativa semi-autonoma creata per conseguire gli obiettivi aziendali strategici. | Viene utilizzata per il reporting finanziario basato su settori o linee di prodotti che l'organizzazione serve indipendentemente dalle persone giuridiche. |
| Flusso del valore        | Unità operativa che controlla uno o più flussi di produzione. | Viene usato solitamente nella produzione snella per controllare le attività e i flussi necessari per la fornitura di un prodotto o di un servizio ai clienti. |
| Reparto          | Unità operativa che rappresenta una categoria o parte funzionale di un'organizzazione che svolge attività specifiche, ad esempio la vendita o la contabilità. | Serve per il reporting sulle aree funzionali. Un reparto può avere responsabilità di profitti e perdite e può comprendere un gruppo di centri di costo. |
| Canale di vendita al dettaglio      | Un'unità operativa rappresenta un punto vendita fisico, un punto vendita online o un marketplace online. | Utilizzato per il controllo di gestione e operativo di uno o più punti vendita tra le persone giuridiche. |

### <a name="teams"></a>Team

Un team è un'organizzazione i cui membri condividono una responsabilità, un interesse o un obiettivo comune. I team non possono essere utilizzati in gerarchie organizzative.

## <a name="organizational-hierarchies"></a>Gerarchie organizzative

Impostare le gerarchie organizzative per la visualizzazione e il reporting sull'attività aziendale da diverse prospettive. È possibile impostare, ad esempio, una gerarchia di persone giuridiche per il reporting fiscale, legale o statutario. Impostare una gerarchia che si basa sulle unità operative per il reporting di informazioni finanziarie non obbligatorio per legge, ma utilizzato per il controllo interno. È ad esempio possibile creare una gerarchia per gli acquisti che controlli i criteri di acquisto, le relative regole e processi aziendali.

A ogni gerarchia viene assegnato uno scopo in Microsoft Dynamics 365 for Finance and Operations. Lo scopo di una gerarchia determina i tipi di organizzazioni che è possibile includere nella gerarchia. Lo scopo consente inoltre di determinare gli scenari di applicazione per la gerarchia.

Le organizzazioni di una gerarchia possono condividere parametri, criteri e transazioni. Le organizzazioni possono ereditare o sostituire i parametri della relativa organizzazione padre. Tuttavia, i dati master condivisi, ad esempio prodotti e rubriche, vengono applicati a tutta l'organizzazione e non possono essere sostituiti per le singole organizzazioni. La creazione di organizzazioni e gerarchie richiede una pianificazione attenta. Per ulteriori informazioni, vedere [Pianificazione della gerarchia organizzativa](plan-organizational-hierarchy.md).
