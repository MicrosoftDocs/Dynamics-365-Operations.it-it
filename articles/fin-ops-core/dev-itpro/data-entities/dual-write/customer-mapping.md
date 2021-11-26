---
title: Gestione integrata dei dati dei clienti
description: In questo argomento viene descritta l'integrazione dei dati dei clienti tra Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 48070628aafd7daac65327a484c87dc01ffb3954
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781692"
---
# <a name="integrated-customer-master"></a>Dati master clienti integrati

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I dati dei clienti possono essere masterizzati in più di un'applicazione Dynamics 365. Ad esempio, una riga del cliente può avere origine dall'attività di vendita in Dynamics 365 Sales (un'app Customer Engagement) o una riga può avere origine dall'attività di vendita al dettaglio in Dynamics 365 Commerce (un'app finance and operations). Indipendentemente da dove provengano i dati dei clienti, questi vengono integrati in background. Dati master clienti integrati ti offre la flessibilità di gestire i dati dei clienti in qualsiasi applicazione Dynamics 365 e offre una visione completa del cliente con la suite di applicazioni Dynamics 365.

## <a name="customer-data-flow"></a>Flusso dei dati dei clienti

*Cliente* è un concetto ben definito nelle applicazioni. Di conseguenza, l'integrazione dei dati dei clienti implica solo armonizzare il concetto di cliente tra due applicazioni. L'illustrazione seguente mostra il flusso dei dati dei clienti.

![Flusso di dati dei clienti.](media/dual-write-customer-data-flow.png)

I clienti possono essere classificati largamente in due tipi: clienti commerciali/aziendali e consumatori/utenti finali. Questi due tipi di clienti vengono archiviati e gestiti in modo diverso in Finance and Operations e Dataverse.

In Finance and Operations, sia i clienti commerciali/aziendali che i consumatori/utenti finali vengono gestiti in un'unica tabella denominata **CustTable** (CustCustomerV3Entity) e vengono classificati in base all'attributo **Tipo**. Se **Tipo** è impostato su **Organizzazione**, il cliente è cliente commerciale/aziendale e se **Tipo** è impostato su **Persona**, il cliente è un consumatore/utente finale. Le informazioni principali del contatto vengono gestite tramite la tabella SMMContactPersonEntity.

In Dataverse, i clienti commerciali/aziendali sono gestiti nella tabella Conto e vengono identificati come clienti quando l'attributo **RelationshipType** è impostato su **Cliente**. Sia i consumatori/utenti finali che il contatto sono rappresentati dalla tabella Contatto. Per fornire una netta separazione tra un consumatore/utente finale e un contatto, la tabella **Contatto** include un flag booleano **Di vendita**. Se **Di vendita** è **True**, il contatto è un consumatore/utente finale e offerte e gli ordini possono essere creati per quel contatto. Se **Di vendita** è **False**, il contatto è solo un contatto principale di un cliente.

Quando un contatto non di vendita partecipa a un processo di ordine o offerta, **Di vendita** è impostato su **True** per contrassegnare il contatto come contatto di vendita. Un contatto che è diventato un contatto di vendita rimane tale.

## <a name="templates"></a>Modelli

I dati dei clienti includono tutte le informazioni sul cliente, ad esempio il gruppo di clienti, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura e lo stato del programma fedeltà. Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con i dati dei clienti, come illustrato nella seguente tabella.

App Finance and Operations | App di interazione con i clienti         | descrizione
----------------------------|---------------------------------|------------
[Contatti CDS V2](mapping-reference.md#115) | contatti | Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
[Gruppi di clienti](mapping-reference.md#126) | msdyn_customergroups | Questo modello sincronizza le informazioni del gruppo di clienti.
[Metodo di pagamento clienti](mapping-reference.md#127) | msdyn_customerpaymentmethods | Questo modello sincronizza le informazioni del metodo di pagamento dei clienti.
[Clienti V3](mapping-reference.md#101) | conti | Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali.
[Clienti V3](mapping-reference.md#116) | contatti | Questo modello sincronizza i dati master per i clienti e gli utenti finali.
[Affissi nome](mapping-reference.md#155) | msdyn_nameaffixes | Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.
[Righe giorno di pagamento - CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.
[Giorni di pagamento - CDS](mapping-reference.md#158) | msdyn_paymentdays | Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
[Righe scadenzario pagamenti](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.
[Scadenzario pagamenti](mapping-reference.md#160) | msdyn_paymentschedules | Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.
[Termini di pagamento](mapping-reference.md#161) | msdyn_paymentterms | Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
