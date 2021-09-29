---
title: Parametri globali del dispositivo mobile
description: Questo argomento spiega come configurare le impostazioni del dispositivo mobile nella pagina dei parametri di gestione del magazzino.
author: HuberIvan
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-huberivan
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 03c10232d55c99c73e625170797f89f6c77e812b
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505579"
---
# <a name="global-mobile-device-parameters"></a>Parametri globali del dispositivo mobile

[!include [banner](../includes/banner.md)]

Questo argomento spiega come impostare i parametri di gestione del magazzino globali che influiscono sul modo in cui il sistema interagisce con i dispositivi mobili.

Per ulteriori informazioni su come impostare gli addetti magazzino, vedi [Gestire l'addetto magazzino](manage-warehouse-workers.md). Per altre informazioni relative alla gestione della targa nei dispositivi mobili, vedi [Ricezione della targa tramite l'app per dispositivi mobili Gestione magazzino](warehousing-mobile-device-app-license-plate-receiving.md). Per ulteriori informazioni sui processi di conteggio dei cicli, vedi [Conteggio del ciclo](cycle-counting.md) e [Scenari di esempio di conteggio del ciclo](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Aprire la pagina Parametri di gestione magazzino

Per aprire la pagina **Parametri di gestione magazzino** vai a **Gestione magazzino \> Impostazioni \> Parametri di gestione magazzino**. Puoi quindi impostare i campi correlati al funzionamento dei dispositivi mobili, come descritto nella sezione successiva di questo argomento.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Scheda dettaglio Dispositivo mobile nella scheda Generale

Le impostazioni globali del dispositivo mobile si trovano nella scheda dettaglio **Dispositivo mobile** della scheda **Generale** della pagina **Parametri di gestione magazzino**. Sono disponibili i campi seguenti.

| Campo | descrizione |
|---|---|
| Tipo di nota del dispositivo mobile | Seleziona il tipo di informazioni visualizzate ai lavoratori durante il prelievo dell'ordine cliente. |
| Limite quantità letta tramite scanner | Immetti la quantità massima di articoli che un lavoratore può scansionare durante ogni sessione utilizzando una voce di menu del dispositivo mobile che ha un valore **Processo di creazione lavoro** di *Rettifica in entrata*. Questo campo non influisce sulle scansioni eseguite utilizzando qualsiasi altro tipo di voce di menu. |
| Utilizza la registrazione sessioni dispositivo mobile | Imposta questa opzione su *Sì* per mantenere un log della cronologia degli accessi dei lavoratori. Per visualizzare il log, vai a **Sessioni utenti di lavoro \> Richieste di informazioni e report \> Log dispositivo mobile \> Sessioni utente di lavoro**. |
| Numero di errori archiviati | Immetti il numero massimo di record di errore che il sistema deve memorizzare. Per visualizzare il log degli errori, vai a **Sessioni utenti di lavoro \> Richieste di informazioni e report \> Log dispositivo mobile \> Sessioni utente di lavoro**. |
| Giornale di registrazione predefinito trasferimento magazzino | Seleziona il giornale utilizzato quando i lavoratori utilizzano un dispositivo mobile per spostare i prodotti da un magazzino all'altro. |
| Consenti registrazione riga ordine fornitore in revisione esterna | Imposta questa opzione su *Sì* se i lavoratori devono essere in grado di utilizzare un dispositivo mobile per registrare le righe d'ordine per gli ordini fornitore che hanno un valore **Stato di approvazione** di *In revisione esterna*. Imposta questa opzione su *No* per impedire ai lavoratori di registrare le righe per ordini fornitore in fase di revisione esterna. |
| Abilita supporto RSAT | Il campo abilita il validator dell'attività dell'app per dispositivi mobili Gestione magazzino, che registra e convalida ogni passaggio eseguito dall'app. Poiché questo processo può rallentare notevolmente le prestazioni del sistema, è necessario abilitare il validator solo durante il test. Non dovresti mai abilitarlo in un ambiente di produzione. |
