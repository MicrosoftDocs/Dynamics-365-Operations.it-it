---
title: Parametri di gestione degli sconti
description: In questo argomento viene descritta la pagina dei parametri di gestione degli sconti. Questa pagina contiene impostazioni che influenzano la registrazione, gli aggiornamenti di stato, le sequenze di numeri e altri comportamenti.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: dc41df33d01c3c8523afb6d8f16bfec88e0c42b8
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271031"
---
# <a name="rebate-management-parameters"></a>Parametri di gestione degli sconti

[!include [banner](../includes/banner.md)]

La pagina **Parametri di gestione degli sconti** viene utilizzata per definire le impostazioni che si applicano a tutto il modulo **Gestione degli sconti**. Queste impostazioni influenzano la registrazione, gli aggiornamenti di stato, le sequenze di numeri e altri comportamenti. La configurazione in questa pagina è condivisa tra le persone giuridiche e può essere modificata dagli utenti che dispongono delle autorizzazioni di sicurezza appropriate.

Per aprire la pagina **Parametri di gestione degli sconti**, vai a **Gestione degli sconti \> Impostazioni \> Parametri di gestione degli sconti**. Quindi imposta i campi come descritto nelle sottosezioni seguenti.

## <a name="rebate-management-tab"></a>Scheda Gestione degli sconti

La tabella seguente descrive i campi disponibili nella scheda **Gestione degli sconti** della pagina **Parametri di gestione degli sconti**.

| Campo | descrizione |
|---|---|
| Stato predefinito | Seleziona lo stato predefinito per tutte le nuove transazioni. Per definire il set di valori di stato disponibile per la selezione, utilizza la pagina [**Stati di sconto**](rebate-statuses.md). |
| Elabora per dimensione | Seleziona se le transazioni di accantonamento, sconto e annullamento devono essere elaborate in base alla dimensione finanziaria. Quando questa opzione è attivata, il sistema utilizza le dimensioni finanziarie dalle transazioni di origine nelle transazioni di destinazione. |
| Controlla se precedentemente registrato | <p>Seleziona il comportamento del sistema se le transazioni di sconto non registrate vengono elaborate più di una volta per lo stesso periodo:</p><ul><li>**Avviso** - Il sistema consente agli utenti di sovrascrivere le righe delle transazioni originali, ma viene visualizzato un avviso.</li><li>**Errore** - Il sistema impedisce agli utenti di sovrascrivere le righe delle transazioni originali e viene visualizzato un messaggio di errore. |
| Registra automaticamente giornali di registrazione | Seleziona se il sistema deve registrare automaticamente i giornali di registrazione proposti. Tali giornali di registrazione includono i giornali giornalieri utilizzati per gli accantonamenti e le detrazioni dei clienti e anche i giornali di registrazione delle fatture fiscali del fornitore. |
| Registra automaticamente fatture a testo libero | Seleziona se il sistema deve registrare automaticamente le fatture a testo libero. Questa opzione si applica solo alle fatture a testo libero in cui il tipo di pagamento è impostato su *Detrazioni cliente fattura fiscale*. |
| Riferimento ordine articolo di sconto | Seleziona il riferimento dello sconto da utilizzare sugli ordini cliente e fornitore generati dal processo di sconto (*Nessuno*, *Transazioni per la gestione degli sconti*, *Numero di gestione degli sconti*, *Numero di transazione sconto*, o *Note documenti*). |
| Usa processo richiesta | <p>Imposta questa opzione su *Sì* per utilizzare il processo di richieste. In questo modo, puoi contrassegnare le transazioni che la gestione degli sconti crea come richieste o non richieste, quindi registrare solo le transazioni richieste.</p><p>Ad esempio, calcola gli sconti per un mese di transazioni, ma il cliente ha lasciato due giorni non richiesti. In questo caso, le transazioni non richieste verranno ricreate la prossima volta che si esegue la funzione *Elabora* per il periodo successivo.</p><p>Se imposti questa opzione su *No*, vengono registrate tutte le transazioni di richiesta.</p> |
| Includi giornale di registrazione tipo di ordine | Per le transazioni o righe di transazione in cui il tipo di transazione è impostato su *Ordine*, questa opzione controlla se un ordine cliente di tipo *giornale di registrazione* deve essere incluso. Fornisce flessibilità se questi tipi di ordini vengono utilizzati in scenari in cui uno sconto non deve ancora essere applicato. |

## <a name="number-sequences-tab"></a>Scheda Sequenze numeriche

Utilizza la scheda **Sequenze numeriche** della pagina **Parametri di gestione degli sconti** per assegnare codici di sequenza numerica alle diverse sequenze numeriche utilizzate dalla gestione degli sconti. La tabella seguente descrive lo scopo di ciascuna di queste sequenze numeriche. Per ulteriori informazioni sulle sequenze numeriche, vedi [Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) e argomenti correlati.

| Riferimento | descrizione |
|---|---|
| Transazione di gestione degli sconti | La sequenza numerica assegna un valore chiave univoco a ciascuna transazione di sconti. Questa chiave viene utilizzata quando vengono create le transazioni. |
| Numero di gestione degli sconti | La sequenza numerica assegna un valore chiave univoco a ciascuno sconto. Questa chiave viene utilizzata per identificare le relazioni di sconto. |
| Numero di transazione sconto | La sequenza numerica assegna un valore chiave univoco a ciascuna transazione di sconto. Questa chiave viene utilizzata per identificare le transazioni di sconto. |
| Fattura fiscale | La sequenza numerica assegna un valore chiave univoco a ciascuna fattura di sconti. Questa chiave viene utilizzata quando i giornali di registrazione degli sconti vengono registrati automaticamente. |

## <a name="feature-visibility-tab"></a>Scheda Visibilità funzionalità

La gestione degli sconti aggiunge funzionalità (campi e funzioni) a diverse pagine utilizzate di frequente in Microsoft Dynamics 365 Supply Chain Management. Queste pagine includono pagine correlate a ordini cliente e transazioni di vendita. Se si utilizza Gestione degli sconti è necessario rendere tali funzionalità visibili ovunque per poterle utilizzare. Se non si utilizza Gestione degli sconti è possibile nascondere queste funzionalità.

Nella scheda **Visibilità funzionalità** della pagina **Parametri di gestione degli sconti**, impostare l'opzione **Attiva** su *Sì* per rendere visibili le funzionalità di gestione degli sconti ovunque siano disponibili. Impostala su *No* per nascondere le funzionalità nelle pagine comuni esterne al modulo **Gestione degli sconti**. Tuttavia, anche quando l'opzione è impostata su *No*, il modulo stesso, inclusa la pagina **Parametri di gestione degli sconti**, rimarrà disponibile per gli utenti che dispongono delle autorizzazioni appropriate per accedervi.
