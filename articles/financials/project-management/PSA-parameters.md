---
title: Parametri di integrazione di Project Service Automation
description: "Questo argomento descrive come configurare la modalità di immissione dei dati predefiniti quando si integra Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 33960a97f69d6bcc70a3035d4d68095ca6993a10
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parametri di integrazione di Project Service Automation

[!include[banner](../includes/banner.md)]

Nella pagina **Parametri di integrazione di Project Service Automation** è possibile configurare la modalità di immissione dei dati predefiniti quando si integra Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 for Finance and Operations. Per una corretta sincronizzazione dei progetti da Project Service Automation a Finance and Operations è necessario impostare i seguenti campi.

> [!NOTE]
> - L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Microsoft Dynamics 365 for Finance and Operations versione 8.0.
> - L'integrazione dei valori effettivi è disponibile in Microsoft Dynamics 365 for Finance and Operations versione 8.0.1 o successive.
> - Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, dopo avere installato gli aggiornamenti KB 4132657 e KB 4132660, sarà possibile utilizzare i modelli per integrare le attività di progetto, le categorie di transazione delle spese, le stime orarie, le stime di spesa e i valori effettivi, nonché di configurare il blocco delle funzionalità. Se è necessario reimpostare le distribuzioni contabili, si consiglia di installare anche KB 4131710.

| Scheda                    | Campo                | descrizione |
|------------------------|----------------------|-------------|
| Generali                | Tipo di progetto predefinito | Selezionare il tipo di progetto predefinito. Quando i progetti vengono sincronizzati da Project Service Automation, viene utilizzato questo valore se non si specifica un valore predefinito nel modello di integrazione. Durante la sincronizzazione, il campo **Tipo di progetto** dei nuovi progetti è impostato su questo valore. Tuttavia, il valore può essere aggiornato quando le righe del contratto di progetto vengono sincronizzate da Project Service Automation. |
|                        | Categoria tempo        | Selezionare la categoria temporale predefinita. Questo valore viene utilizzato quando vengono sincronizzate le stime relative alle ore da Project Service Automation. Quando si esegue la sincronizzazione delle stime orarie e dei valori orari effettivi da Project Service Automation, il campo **Categoria** delle nuove previsioni orarie del progetto in Finance and Operations viene impostato su questo valore. |
|                        | Categoria commissioni         | Selezionare la categoria di commissioni predefinita. Questo valore viene utilizzato quando vengono sincronizzate le stime relative alle commissioni da Project Service Automation. Quando i valori effettivi di commissioni vengono sincronizzati da Project Service Automation, il campo **Categoria** delle nuove transazioni di commissioni in Finance and Operations viene impostata su questo valore. |
| Valori predefiniti del gruppo di progetti | Tipo di progetto         | Fare clic su **Nuovo** per aggiungere una riga dove è possibile selezionare il tipo di progetto per cui impostare il gruppo di progetti predefinito. È possibile selezionare un tipo di progetto specifico solo una volta nella configurazione. |
|                        | Gruppo di progetti        | Selezionare il gruppo di progetti predefinito per il tipo di progetto selezionato. Quando i nuovi progetti vengono sincronizzati da Project Service Automation, il campo **Gruppo di progetti** viene impostato sul valore predefinito per il tipo di progetto se non è stato specificato un valore predefinito nel modello di integrazione. |
| Impostazioni predefinite tipo di fatturazione  | Tipo di fatturazione         | Fare clic su **Nuovo** per aggiungere una riga dove è possibile selezionare il tipo di fatturazione per cui impostare la proprietà di riga predefinita. È possibile selezionare un tipo di fatturazione specifico solo una volta nella configurazione. |
|                        | Proprietà riga        | Selezionare la proprietà di riga predefinita per il tipo di fatturazione selezionato. Quando le nuove stime orarie, le nuove stime di spesa o i nuovi valori effettivi vengono sincronizzati da Project Service Automation, il campo **Proprietà riga** viene impostato sul valore predefinito per il tipo di fatturazione. |
| Blocco funzionalità  | Non applicabile       | Selezionare la funzionalità per disattivare in Finance and Operations per i progetti e i contratti che hanno origine da Project Service Automation. Ad esempio, è possibile disattivare la possibilità di modificare i contratti e i progetti, di creare strutture di suddivisione del lavoro e di immettere fogli presenze in Finance and Operations. I campi correlati alla contabilità continueranno a essere attivati, anche se resi non disponibili dall'impostazione dei parametri. Per impostazione predefinita, tutte le funzionalità sono abilitate. |

