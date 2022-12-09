---
title: Panoramica dell'unione dell'infrastruttura Dynamics 365 Human Resources
description: In questo articolo viene descritta l'unione dell'infrastruttura di Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e68b28bfde35b51605aa0b653265da6261b69a90
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819244"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Unione dell'infrastruttura Dynamics 365 Human Resources 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Human Resources 365

Microsoft Dynamics 365 Human Resources fornisce gli strumenti che aiutano i team HR a migliorare l'agilità organizzativa, trasformare l'esperienza dei dipendenti e ottimizzare i programmi HR per creare un ambiente di lavoro in cui le persone possano avere successo e l'attività possa prosperare. Per altre informazioni su Dynamics 365 Human Resources, vedere [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Trasforma l'esperienza del dipendente.** Trattieni i tuoi migliori elementi fornendo gli strumenti ottimali a manager e dipendenti con esperienze self-service connesse che favoriscono l'impegno e la crescita.
- **Ottimizzazione dei programmi HR.** Contribuisci a ridurre i costi operativi e crea programmi di gestione di congedi e assenze, orario, benefit e retribuzione incentrati sulle persone.
- **Aumento dell'agilità organizzativa.** Consenti al reparto HR di operare con la destrezza richiesta dall'azienda mediante l'uso di Dataverse e Microsoft Power Platform per centralizzare i dati delle persone ed estendere facilmente Dynamics 365 Human Resources.
- **Scopri le informazioni dettagliate sulla forza lavoro.** Prendi decisioni basate sui dati grazie alla possibilità di analizzare e visualizzare i dati delle persone su dashboard avanzati disponibili su qualsiasi dispositivo.

## <a name="human-resources-infrastructure-merge"></a>Unione dell'infrastruttura di Human Resources

Dynamics 365 Human Resources è un'applicazione autonoma che attualmente utilizza un'infrastruttura diversa da altre app per finanza e operazioni, come Dynamics 365 Finance o Dynamics 365 Supply Chain Management. L'unione dell'infrastruttura porterà Dynamics 365 Human Resources nella stessa infrastruttura di altre app per la finanza e le operazioni.

Per altre informazioni sull'unione dell'infrastruttura di Human Resources, vedi [Offerte di unione di Human Resources](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Per le risposte alle domande frequenti, vedi [Domande frequenti sull'unione dell'infrastruttura di Human Resources](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Migrazione dei clienti e unione dei clienti

Nell'ambito dell'unione dell'infrastruttura, tutte le funzionalità dell'applicazione Human Resources sono state rese disponibili negli ambienti per la finanza e le operazioni. I clienti possono migrare i loro ambienti Human Resources utilizzando gli strumenti di migrazione disponibili in Microsoft Dynamics Lifecycle Services. Possono anche unire facoltativamente i loro dati con il loro ambiente per la finanzia e le operazioni esistente. 

La migrazione dei clienti e l'unione dei clienti differiscono nel modo seguente:

- **Migrazione dei clienti** – Gli strumenti di migrazione automatizzata vengono utilizzati per eseguire una "migrazione lift-and-shift" (spostamento) del database dei clienti dall'infrastruttura Human Resources all'infrastruttura per la finanza e le operazioni. Il risultato è un nuovo ambiente per la finanza e le operazioni che utilizza il database Human Resources del cliente. 
- **Unione dei clienti** – Questo passaggio aggiuntivo non è richiesto da Microsoft. Viene fatto a discrezione del cliente e in base alla propria sequenza temporale. Durante questo passaggio, i dati dei clienti vengono spostati in un ambiente esistente, ad esempio un ambiente Finance o Project Operations. È per lo più manuale e può essere eseguito utilizzando le entità di dati Data Management Framework (DMF). 

## <a name="planning-a-human-resources-environment-migration"></a>Pianificazione della migrazione di un ambiente Human Resources

Nell'ambito dell'unione dell'infrastruttura, a tutti i clienti sarà richiesto di migrare i propri ambienti Human Resources esistenti dall'infrastruttura autonoma. Per facilitare questo processo, ti consigliamo di utilizzare gli strumenti di migrazione automatizzata in Lifecycle Services per spostare gli ambienti attuali nella nuova infrastruttura. 

Le sezioni seguenti forniscono maggiori dettagli su come utilizzare gli strumenti di Lifecycle Services per migrare un ambiente autonomo Human Resources. 

I clienti che stanno pianificando una migrazione possono avere le seguenti aspettative:

- Ai tutti clienti verrà richiesto di eseguire la migrazione di un ambiente sandbox prima della migrazione dell'ambiente di produzione. 
- Gli strumenti di migrazione consentono solo la migrazione da sandbox a sandbox e da produzione a produzione. Pertanto, il tipo di ambiente determinerà quale ambiente può essere migrato in modo appropriato. 
- I clienti possono migrare tutte le sandbox necessarie prima di migrare il proprio ambiente di produzione, a condizione che sia disponibile uno slot sandbox di destinazione. I clienti possono anche eliminare una sandbox migrata ed eseguire più volte la migrazione. 
- Se la migrazione di una sandbox non riesce o se vuoi ricominciare da capo, è possibile eliminare un ambiente nell'infrastruttura per la finanza e le operazioni ed eseguire nuovamente la migrazione dello stesso ambiente.
- L'URL del tuo ambiente Human Resources sarà diverso dopo la migrazione.
- Pianifica un periodo di inattività adeguato per la migrazione del tuo ambiente di produzione. Il tempo stimato per il completamento del processo di migrazione automatizzato è di tre o quattro ore. Il periodo di tempo varia a seconda dei dati della tua organizzazione. È necessario convalidare la quantità di tempo necessaria per la migrazione degli ambienti sandbox e concedere il tempo per eventuali attività manuali aggiuntive che devono essere completate.

> [!IMPORTANT] 
> Quando un ambiente di produzione viene migrato correttamente all'infrastruttura per la finanza e le operazioni, l'ambiente di produzione autonomo di origine viene eliminato automaticamente. Non eliminare l'ambiente di produzione migrato. 

Il processo per la migrazione è per lo più automatico. Tuttavia, gli utenti aziendali dovranno completare alcuni passaggi manuali e la convalida dopo la migrazione.

È necessario completare i seguenti passaggi manuali:

- Creare un nuovo progetto Lifecycle Services per la migrazione.
- Rivedere eventuali integrazioni nel vecchio ambiente nel nuovo ambiente indirizzando l'integrazione al nuovo URL/endpoint, in base a ciascuna configurazione di integrazione.
- Aggiornare l'archivio dati per i report Power BI incorporati.
- Aggiornare l'elenco delle entità dati dall'area di lavoro DMF.
- Collegarsi a Lifecycle Services per assistenza.
- Creare un calendario fiscale.

Durante il processo automatico, le seguenti azioni vengono completate e devono essere convalidate:

- Dati:

    - Configurazioni
    - Ruoli di sicurezza (inclusi ruoli personalizzati)
    - Flussi di lavoro (incluse notifiche)
    - Personalizzazioni e visualizzazioni salvate
    - Transazioni
    - Campi personalizzati
    - Allegati
    - Avvisi

- Gestione dati - Portare il proprio database (BYOD).
- Gestione funzionalità - Abilitare/disabilitare le funzionalità.
- Power Apps incorporato.
- Ambiente collegato all'interfaccia di amministrazione di Power Platform (solo produzione).
- Processi batch.
- Viene creata una contabilità generale vuota per ogni persona giuridica. Vengono impostati il tipo di tasso di cambio predefinito e la valuta contabile per ciascuna contabilità generale.
- Un nuovo piano dei conti viene creato automaticamente e collegato alla pagina **Contabilità generale** in ciascuna persona giuridica. Le dimensioni finanziarie configurate nell'ambiente Human Resources verranno automaticamente aggiunte a una nuova struttura dei conti e collegate alla contabilità generale. 

> [!NOTE]
> È necessario una contabilità generale per l'infrastruttura per la finanza e le operazioni come parte del prodotto Dynamics 365 Finance. Il controller delle dimensioni personalizzate che esisteva nell'applicazione autonoma Dynamics 365 Human Resources non è disponibile. L'infrastruttura unita per Human Resources dipende dalla logica di Finance per mostrare le dimensioni finanziarie nel modulo **Human Resources**. Per ulteriori informazioni sul piano dei conti e sulle dimensioni finanziarie, vedi [qui](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Considerazioni

- La migrazione agli ambienti avverrà sempre nell'ultima versione generalmente disponibile (GA). A seconda del piano di migrazione e test, se la convalida della migrazione per gli ambienti sandbox era su una versione diversa, ti consigliamo di convalidare una migrazione sandbox sulla stessa versione dell'ambiente di produzione. 
- Durante la migrazione, gli ambienti migrati verranno collocati nella stessa area geografica degli ambienti autonomi Human Resources di origine.

## <a name="licensing"></a>Licenze

Non ci sono modifiche alla licenza per Dynamics 365 Human Resources nelle seguenti aree: 

- **Requisito minimo per l'acquisto della licenza**
- **Licenze per un ambiente di produzione e un ambiente sandbox** – Se disponi di licenze Human Resources autonome esistenti che includono un ambiente di produzione e un ambiente sandbox, lo stesso numero di licenze sarà disponibile sull'infrastruttura per la finanza e le operazioni, senza costi aggiuntivi.
- **Licenze sandbox aggiuntive** – Se hai acquistato licenze sandbox aggiuntive per l'applicazione autonoma Human Resources, lo stesso numero di licenze sandbox è disponibile per un ambiente standard di test di accettazione (sandbox) sull'infrastruttura per la finanza e le operazioni, senza costi aggiuntivi. 
