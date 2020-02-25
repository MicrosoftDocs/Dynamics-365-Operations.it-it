---
title: Panoramica di Credito e riscossioni
description: In questo argomento viene fornita una panoramica della funzionalità Credito e riscossioni.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2fdfe05483d577819d64bdf7a4ebfe5d37cd414c
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015272"
---
# <a name="credit-and-collections-overview"></a>Panoramica di Credito e riscossioni

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

È possibile gestire i limiti di credito per i clienti ed eseguire attività di riscossione quando diventano necessarie.

## <a name="credit-management"></a>Gestione crediti

La gestione dei crediti cliente consente di gestire i limiti di credito e di controllare il flusso degli ordini cliente attraverso il processo di registrazione in base a regole di credito create.

Il processo di gestione dei crediti può includere alcuni o tutti i seguenti passaggi:

- Aggiornare attributi di credito per i clienti allo scopo di fornire ulteriori informazioni sulla loro affidabilità creditizia.
- Creare limiti di credito per i clienti utilizzando correzioni dei limiti di credito.
- Creare limiti di credito temporanei per i clienti utilizzando correzioni dei limiti di credito. In questo modo, è possibile aumentare o ridurre temporaneamente i limiti di credito dei clienti in base ai requisiti aziendali.
- Aggiungere ulteriori informazioni che possono influire sul limite di credito come informazioni su assicurazione e garanzie.
- Crea gruppi di crediti cliente che collegano i clienti di modo che possano condividere un unico limite di credito.
- Assegnare punteggi di rischio ai clienti e quindi utilizzare tali punteggi per generare automaticamente limiti di credito per quei clienti utilizzando correzioni dei limiti di credito.
- Creare regole di blocco che sospenderanno un ordine durante uno o più processi di registrazione in base a fattori quali rischio, termini di pagamento, limiti di credito, importi scaduti e percentuale del limite di credito utilizzato.
- Gestire un elenco di ordini cliente sospesi, esaminare i motivi della sospensione e attenuare i problemi.
- Rilasciare ordini cliente in modo da continuare il processo di registrazione degli stessi.
- Configurare un flusso di lavoro per gestire l'approvazione delle modifiche a limiti di credito e dei rilasci di ordini cliente.

## <a name="collections-management"></a>Gestione raccolte

La pagina **Riscossioni** fornisce una visualizzazione centralizzata per la gestione delle informazioni sulle riscossioni della contabilità clienti. I responsabili delle riscossioni possono utilizzare questa visualizzazione per gestire le riscossioni. Gli agenti di riscossione possono avviare il processo di riscossione dagli elenchi di clienti generati utilizzando criteri di riscossione predefiniti o dalla pagina **Clienti**.

Prima di iniziare a impostare o a utilizzare le riscossioni, è necessario comprendere i concetti seguenti:

- Gli snapshot di aging dei clienti contengono informazioni sui saldi con aging in un momento specifico nel tempo.
- I pool di clienti per riscossioni facilitano l'organizzazione del lavoro.
- Gli agenti di riscossione possono avere pool di clienti propri.
- Le pagine elenco consentono di organizzare casi, attività e clienti di riscossione.
- Tutte le informazioni sulle riscossioni relative a un cliente si trovano in un'unica pagina in cui è possibile intraprendere le azioni necessarie.
- È possibile rinunciare a interessi e commissioni, ripristinarli oppure stornarli in un unico passaggio.
- È possibile creare transazioni di annullamento in un unico passaggio.
- È possibile elaborare pagamenti NSF (Non Sufficient Funds, senza copertura) in un unico passaggio.

Per le descrizioni di questi concetti, vedere [Concetti chiave della gestione delle riscossioni](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostazione dei parametri di gestione dei crediti cliente](./cm-credit-mgmt-setup.md)

[Informazioni sull'impostazione della gestione dei crediti cliente](./cm-setup-information.md)

[Aggiungere informazioni sulla gestione dei crediti per un cliente](./cm-add-credit-mgmt-information-customer.md)

[Gruppi di crediti cliente](./cm-customer-credit-groups.md)

[Correzioni dei limiti di credito dei clienti](./cm-credit-limit-adjustments.md)

[Sospensioni credito per ordini cliente](./cm-sales-order-credit-holds.md)

[Attività periodiche di gestione dei crediti cliente](./cm-periodic-tasks.md)
