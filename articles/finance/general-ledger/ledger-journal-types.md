---
title: Tipi di giornale di registrazione contabilità generale
description: In questo argomento vengono descritti i tipi di giornale di registrazione che è possibile impostare per i giornali di registrazione finanziari.
author: ShylaThompson
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f215b31df120d152a84e994fbe9de739385ce836
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988729"
---
# <a name="ledger-journal-types"></a>Tipi di giornale di registrazione contabilità generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i tipi di giornale di registrazione che è possibile impostare per i giornali di registrazione finanziari. Utilizzare la pagina **Nomi giornale** di registrazione per impostare i giornali di registrazione che è possibile utilizzare con Dynamics 365 Finance.

| Tipo giornale di registrazione                      | Scopo                       | Immettere le transazioni in questa pagina                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Allocazione                        | Creare transazioni di allocazione in un giornale di registrazione allocazioni. Prima di poter creare un giornale di registrazione allocazioni, è necessario creare una regola di allocazione nella pagina **Regola di allocazione contabile**.      | Elabora richiesta di allocazione             |
| Approvazione                          | Registrare le fatture fornitore approvate nei conti CoGe appropriati.  | Giornale di approvazione fatture                                       |
| Storno assegno bancario               | Stornare un assegno registrato. Per utilizzare questo tipo di giornale di registrazione, selezionare l'opzione **Usa processo di revisione per storni di pagamenti** nella pagina **Parametri di gestione cassa e banche**.   | Storni di assegni, storno di pagamento                   |
| Annullamento distinta di deposito bancario    | Annullare una distinta di deposito. Per utilizzare questo tipo di giornale di registrazione, selezionare l'opzione **Usa processo di revisione per annullamenti di distinte di deposito bancario** nella pagina **Parametri di gestione cassa e banche**.   | Annullamento distinte di deposito bancario            |
| Budget                            | Elaborare le ripartizioni di budget. Per utilizzare questo tipo di giornale di registrazione, selezionare **Abilita ripartizione budget** nella pagina **Parametri di contabilità generale**. Le voci del giornale di registrazione budget comprenderanno le informazioni basate sui conti CoGe definiti nella pagina **Definizioni di registrazione**.                                                        |                                                                |
| Effetto attivo cliente accettato  | Creare transazioni relative all'accettazione del cliente per effetti attivi.             | Giornale di registrazione effetti attivi emessi, giornale di registrazione effetti attivi riemessi |
| Rimessa bancaria cliente          | Creare un file di rimesse di effetti attivi che può essere inviato alla banca dell'organizzazione. Per utilizzare questo tipo di giornale di registrazione, deselezionare l'opzione **Liquidazione automatica** nella pagina **Parametri** **contabilità clienti**.            | Rimessa                                                     |
| Effetto attivo cliente emesso    | Creare transazioni relative a effetti attivi cliente emessi. Per utilizzare questo tipo di giornale di registrazione, deselezionare l'opzione **Crea e registra automaticamente il giornale emissioni durante la registrazione delle fatture** nella pagina **Metodi di pagamento - Clienti**.   | Giornale di registrazione effetti attivi emessi                                  |
| Pagamento cliente                  | Creare transazioni di pagamento cliente.                             | Giornale di registrazione pagamenti             |
| Effetto attivo cliente protestato | Creare transazioni relative a effetti attivi cliente protestati.                    | Giornale di registrazione effetti attivi protestati                               |
| Effetto attivo cliente riemesso  | Creare transazioni relative a effetti attivi cliente riemessi.                     | Giornale di registrazione effetti attivi riemessi                                |
| Effetto attivo cliente liquidato  | Creare transazioni relative a effetti attivi cliente liquidati.                       | Giornale di registrazione effetti attivi liquidati                                |
| Giornaliero                             | Creare transazioni giornaliere in un giornale di registrazione generale.                          | Giornale di registrazione generale                                                |
| Eliminazione                       | Creare transazioni di eliminazione in un giornale di registrazione eliminazioni. Per utilizzare questo tipo di giornale di registrazione, selezionare le opzioni **Utilizza per processo di eliminazione finanziario** e **Utilizza per processo di consolidamento finanziario** nella pagina **Persone giuridiche**. Prima di poter utilizzare questo tipo di giornale di registrazione, è necessario creare una regola di eliminazione contabile nella pagina **Regola di eliminazione contabile**. | Eliminazione                                                    |
| Budget cespiti                | Creare le voci del registro di budget cespiti.                                                                                                                                                                                                                                                                                                                 | Budget cespiti                                             |
| Registro fatture                  | Registrare le informazioni principali sulle fatture fornitore.                                                                                                                                                                                                                                                                                                           | Registro fatture                                               |
| Esborso retribuzioni              | Emettere pagamenti che si basano sulle istruzioni di pagamento delle retribuzioni. Non è possibile immettere manualmente le transazioni in questo giornale di registrazione. È necessario generare le istruzioni di pagamento e quindi inviare tali istruzioni per il pagamento.                                                                                                                                                              |                                                                |
| Periodico                          | Creare transazioni periodiche per il giornale di registrazione periodico.                                                                                                                                                                                                                                                                                                      | Giornali di registrazione periodici                                              |
| Registra cespiti                 | Registrare transazioni cespiti.                                                                                                                                                                                                                                                                                                                              | Cespiti                                                   |
| Progetto - Spese                | Creare transazioni di spesa del progetto.                                                                                                                                                                                                                                                                                                                        | Expense                                                        |
| Rettifica valuta di dichiarazione     | Creare rettifiche nella valuta di dichiarazione per i saldi dei conti CoGe.               | Giornali di registrazione rettifiche valuta di dichiarazione                         |
| Transazioni statistiche            | Creare transazioni statistiche.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Rimessa bancaria fornitore            | Creare un file di rimesse di effetti passivi che può essere inviato alla banca dell'organizzazione.                                                                                                                                                                                                                                                                      | Giornale di registrazione rimesse                                             |
| Esborso fornitore               | Creare transazioni di esborso fornitore.                                                                                                                                                                                                                                                                                                                    | Giornale di registrazione pagamenti                                                |
| Effetto passivo fornitore emesso       | Emettere effetti passivi fornitore come metodo di pagamento. Per utilizzare questo tipo di giornale di registrazione, deselezionare l'opzione **Crea e registra automaticamente il giornale emissioni durante la registrazione delle fatture** nella pagina **Metodi di pagamento - Fornitori**.                                                                                                                                          | Giornale di registrazione effetti passivi emessi                                   |
| Pool di fatture fornitore, registrazione esclusa | Creare transazioni fatture fornitore che non sono state ancora registrate in un conto arrivi temporaneo.                                                                                                                                                                                                                                                             | Pool di fatture fornitore esclusi i dettagli di registrazione                  |
| Pool fatture fornitore               | Creare transazioni relative a pool di fatture fornitore.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Registrazione fattura fornitore          | Registrare le fatture fornitore che si trovano in un giornale di registrazione.                                                                                                                                                                                                                                                                                                                 | Giornale di registrazione fatture                                                |
| Effetto passivo fornitore riemesso     | Riemettere un effetto passivo che è stato precedentemente onorato dalla banca dell'organizzazione.                                                                                                                                                                                                                                                                      | Giornale di registrazione effetti passivi riemessi                                 |
| Effetto passivo fornitore liquidato     | Creare transazioni relative a effetti passivi fornitore liquidati.                                                                                                                                                                                                                                                                                                          | Giornale di registrazione effetti passivi liquidati                                 |





