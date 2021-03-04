---
title: Configurare conti di registrazione leasing
description: Questo argomento elenca i conti di registrazione richiesti per le transazioni di Leasing cespite e spiega come definire i conti di registrazione nella pagina Parametri di registrazione del leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8ca1c6eea854577e5aa34b1a9b9d1731b209527b
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444973"
---
# <a name="set-up-lease-posting-accounts"></a>Configurare conti di registrazione leasing

[!include [banner](../includes/banner.md)]

Questo argomento elenca i conti di registrazione richiesti per le transazioni di Leasing cespite e spiega come definire i conti di registrazione nella pagina **Parametri di registrazione del leasing**.

Per essere conformi ai principi Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16), potrebbe essere necessario creare i conti nel piano dei conti. Tuttavia, tutti i conti creati per conformarsi agli standard ASC e IFRS non sono conti cespite. Ai sensi di ASC 842, viene registrato un asset Right of use (ROU) sia per i leasing finanziari che per quelli operativi. Questi leasing sono separati dai cespiti. (È comunque possibile mantenere un asset ROU utilizzando Cespiti.)

Per ulteriori informazioni su come creare le strutture di conti, vedi [Creare le strutture dei conti](../general-ledger/tasks/create-account-structures.md). Per ulteriori informazioni su come creare un conto principale, vedi [Creare un conto principale](../general-ledger/tasks/create-main-account.md).

La tabella seguente mostra esempi di conti che è necessario creare per transazioni di asset in leasing, se non sono già stati creati. Ai sensi di IFRS 16, le relazioni di leasing operativi sono ancora utilizzate per i leasing di basso valore e a breve termine.

| Numero conto CoGe | Tipo di account  | Nome conto                                          |
|-----------------------|---------------|-------------------------------------------------------|
| 180150                | AttivitÃ          | Asset ROU del veicolo                                     |
| 180160                | AttivitÃ          | Asset ROU edificio                                    |
| 180250                | AttivitÃ          | Ammortamento accumulato - veicoli                   |
| 180260                | AttivitÃ          | Ammortamento accumulato - edifici                  |
| 222300                | Passività     | Obbligo a breve termine - leasing finanziari                |
| 222310                | Stato patrimoniale | Obbligo a breve termine - leasing operativi              |
| 250200                | Passività     | Effetti passivi                                         |
| 250601                | Stato patrimoniale | Obbligo a lungo termine - leasing finanziari                 |
| 250602                | Stato patrimoniale | Obbligo a lungo termine - leasing operativi               |
| 250606                | Stato patrimoniale | Passività sui contratti                                         |
| 300160                | Stato patrimoniale | Utili non distribuiti                                     |
| 604500                | Gestione spese       | Costo di leasing                                         |
| 604501                | Gestione spese       | Spese per leasing operativo di veicoli - incremento degli interessi  |
| 604502                | Gestione spese       | Spese per leasing operativo di veicoli - ammortamento        |
| 605200                | Gestione spese       | Spese per leasing operativo di edifici - incremento degli interessi |
| 605201                | Gestione spese       | Spese per leasing operativo di edifici - ammortamento       |
| 607101                | Gestione spese       | Spesa per ammortamento leasing di veicoli                    |
| 607102                | Gestione spese       | Spese per ammortamento leasing di edifici                   |
| 607103                | Gestione spese       | Oneri per riduzione di valore - leasing finanziari                   |
| 607104                | Gestione spese       | Oneri per riduzione di valore - leasing operativi                 |
| 618910                | Gestione spese       | Costo di leasing - leasing finanziari                        |
| 618920                | Gestione spese       | Pagamenti variabili - leasing finanziari                    |
| 618930                | Gestione spese       | Pagamenti variabili - leasing operativi                  |
| 800600                | Gestione spese       | Interesse passivo leasing di veicoli                        |
| 800601                | Gestione spese       | Interesse passivo leasing di edifici                       |
| 801201                | Stato patrimoniale | Profitti/Perdite - modifica del leasing                      |

## <a name="configure-posting-accounts"></a>Configurare conti di registrazione

Per assegnare conti ai libri di leasing e ai gruppi che sono stati creati, è necessario configurare i parametri per Leasing cespite.

1. Vai a **Leasing cespite \> Imposta \> Parametri di registrazione del leasing**.
2. Nella scheda **Conti**, apri la Scheda dettaglio **Conti di leasing**. Determina i conti principali per i leasing finanziari e operativi in base al corrispondente **Tipo di registrazione**. La tabella precedente mostra i conti relativi a leasing operativi e finanziari.

    > [!NOTE]
    > Questo passaggio richiede la configurazione di conti separati per i leasing operativi e finanziari per ogni tipo di registrazione eccetto **Compensazione spese di leasing** e **Aumento/diminuzione leasing**. Le società che aderiscono al framework di contabilità IFRS 16 devono aggiungere un conto principale per il leasing operativo. Ma il sistema non utilizzerà questo conto anche se è un campo obbligatorio perché tutti i leasing ai sensi di IFRS 16 sono classificati come leasing finanziari.
    >[!NOTE]
    > **Aumento/diminuzione leasing** verrà utilizzato come tipo di registrazione per ulteriori considerazioni sui cespiti, tra cui **Costo diretto iniziale, Incentivi di leasing, Pagamenti anticipati di leasing e Costi di smantellamento**, ma registra nell'account principale dell'asset Right of use che per impostazione predefinita è **Cespite leasing**.        
    
3. Per selezionare un gruppo di leasing specifico corrispondente al conto principale, nel campo **Codice conto**, seleziona **Gruppo**. Quindi, nel campo **Numero di conto/gruppo** seleziona il gruppo di leasing da assegnare al conto principale.
4. Per assegnare i codici conto ai costi amministrativi che sono stati configurati nel sistema, nella Scheda dettaglio **Costi di esecuzione**, nel campo **Tipo di spesa**, seleziona una spesa. Quindi assegna i conti finanziari e operativi da utilizzare per ogni libro.

    > [!NOTE]
    > Il conto finanziario o operativo selezionato verrà addebitato quando viene registrata la fattura per la spesa programmata.
    > **Compensazione delle spese di leasing** verrà utilizzato come tipo di registrazione per le transazioni dei costi di esecuzione ma registrerà nel **Conto di compensazione** definito in **Righe scadenziario pagamenti costi di esecuzione** nei dettagli del leasing o nel modulo del libro di leasing.   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]