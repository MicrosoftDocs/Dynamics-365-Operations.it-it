---
title: Parametri di integrazione di Project Service Automation
description: "È possibile configurare i valori predefiniti dei dati durante l'integrazione di Project Service Automation con Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: it-it
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parametri di integrazione di Project Service Automation

Nella pagina **Parametri di integrazione di Project Service Automation**, è possibile configurare le impostazioni predefinite di dati durante l'integrazione di Project Service Automation con Finance and Operations. Per una corretta sincronizzazione tra Project Service Automation e Finance and Operations è necessario configurare i seguenti elementi per i progetti.

> [!NOTE]
> L'integrazione delle attività di progetto, le categorie di transazione spese, le stime orarie, le stime di spesa e il blocco delle funzionalità sono disponibili in Dynamics 365 for Finance and Operations versione 8.0.




| **Scheda**                      | **Campo**                          | **Descrizione**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Generale**                  | **Tipo di progetto predefinito**               | Selezionare il valore predefinito per **Tipo di progetto**, che è quando i progetti vengono sincronizzati da Project Service Automation se non è stato specificato un valore predefinito nel modello di integrazione. Durante la sincronizzazione, i nuovi progetti avranno **Tipo di progetto** impostato su questo valore e potrebbero essere aggiornati quando le righe di contratto di progetto vengono sincronizzate da Project Service Automation.               |
| **Generale**                  | **Categoria tempo**                      | Selezionare il valore predefinito per **Categoria tempo**, che è quando le stime orarie vengono sincronizzate da Project Service Automation. Durante la sincronizzazione le previsioni orarie dei nuovi progetti in Finance and Operations avranno **Categoria** impostata su questo valore quando le stime orarie e il numero effettivo di ore vengono sincronizzati da Project Service Automation.   |
| **Generale**                  | **Categoria commissioni**                       | Selezionare il valore predefinito per **Categoria commissioni**, che è quando i valori effettivi di commissione vengono sincronizzati da Project Service Automation. Durante la sincronizzazione, le nuove transazioni di commissione in Finance and Operations avranno **Categoria** impostata su questo valore quando i valori effettivi di commissione vengono sincronizzati da Project Service Automation.          |
| **Valori predefiniti del gruppo di progetti**   | **Tipo di progetto** | Fare clic su **Nuovo** per aggiungere una riga dove è possibile selezionare il tipo di progetto per cui impostare il gruppo di progetti predefinito. Un tipo di progetto specifico può essere selezionato solo una volta nella configurazione.              
|                              | **Gruppo di progetti**          | Selezionare il gruppo di progetti predefinito per il tipo di progetto specificato. Quando i nuovi progetti vengono sincronizzati da Project Service Automation, l'impostazione di **Gruppo di progetti** sarà l'impostazione predefinita basata sul tipo di progetto se non è stato fornito un valore predefinito nel modello di integrazione.  |
| **Impostazioni predefinite tipo di fatturazione**    | **Tipo di fatturazione** | Fare clic su **Nuovo** per aggiungere una riga dove è possibile selezionare il tipo di fatturazione per cui impostare la proprietà di riga predefinita. Un tipo di fatturazione specifico può essere selezionato solo una volta nella configurazione.          |
|                              | **Proprietà riga**| Selezionare la proprietà di riga predefinita per il tipo di fatturazione specificato. Quando le nuove stime orarie, le nuove stime di spesa o i nuovi valori effettivi vengono sincronizzati da Project Service Automation, l'opzione **Proprietà riga** verrà impostata come valore predefinito in base al tipo di fatturazione.          |
| **Blocco funzionalità**    |                   | Selezionare la funzionalità per disattivare in Finance and Operations per i progetti e i contratti che hanno origine da Project Service Automation. Ad esempio, è possibile scegliere di disattivare la possibilità di modificare i contratti e i progetti, di creare strutture di suddivisione del lavoro e di immettere fogli presenze in Finance and Operations. I campi correlati alla contabilità continueranno a essere attivati, anche se resi non disponibili dall'impostazione dei parametri. Per impostazione predefinita, tutte le funzionalità saranno attivate.           |

