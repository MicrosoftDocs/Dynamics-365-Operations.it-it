---
title: Definire e gestire canali di vendita al dettaglio
description: Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita al dettaglio in Dynamics 365 Retail. Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita al dettaglio.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 45d0386d215da15103a417502debb245c91f6309
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934610"
---
# <a name="define-and-maintain-retail-channels"></a>Definire e gestire canali di vendita al dettaglio

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica del processo per l'impostazione di punti vendita fisici, denominati punti vendita al dettaglio in Dynamics 365 Retail. Sono riportate informazioni sulle attività da completare prima e dopo la configurazione di un punto vendita al dettaglio.

Retail supporta più canali di vendita al dettaglio, ad esempio negozi online, servizi clienti e punti vendita fisici. Un punto vendita fisico è anche denominato punto vendita al dettaglio. Ogni punto vendita al dettaglio può disporre dei propri metodi di pagamento, gruppi di prezzi, registratori di cassa POS, conti ricavi/spese e personale. È necessario impostare tutti questi elementi per un punto vendita al dettaglio prima di crearlo. Dopo aver creato il punto vendita al dettaglio, assegnare i prodotti che si desidera siano presenti i esso. Inoltre l'utente assegna dipendenti, registratori di cassa e clienti al punto vendita. Infine, aggiungere il nuovo punto vendita a una gerarchia organizzativa.

## <a name="setting-up-retail-stores"></a>Impostazione dei punti vendita al dettaglio

Prima di impostare un punto vendita al dettaglio in Retail, è necessario completare alcune attività previste come prerequisito. È possibile quindi creare il punto vendita al dettaglio e aggiungere i dettagli.

### <a name="prerequisites"></a>Prerequisiti

Prima di impostare un punto vendita al dettaglio, è necessario completare le seguenti attività:

1. Configurare la struttura dell'organizzazione e impostare le gerarchie dell'organizzazione per gli assortimenti di articoli al dettaglio, il rifornimento e il reporting.
2. Impostare un magazzino che rappresenti il punto vendita al dettaglio.
3. Impostare le sequenze numeriche per i punti vendita al dettaglio, i rendiconti per il punto vendita e i giustificativi dei rendiconti.
4. Configurare i parametri per la vendita al dettaglio.
5. Impostare i metodi di pagamento accettati dal punto vendita.
6. Per elaborare le transazioni con carta di credito nei registratori di cassa Retail POS, è possibile impostare i servizi di pagamento.
7. Impostare le fasce IVA.
8. Impostare i prodotti di vendita al dettaglio. Come parte dell'attività, si impostano anche le gerarchie di prodotti al dettaglio, le varianti prodotto e gli assortimenti prodotto.
9. Impostare i gruppi di prezzo dei prodotti.
10. Impostare i prezzi dei prodotti di vendita al dettaglio. Come parte dell'attività, si impostano anche le rettifiche prezzo, gli sconti e i periodi di sconto.
11. Impostare i membri del personale.

    > [!NOTE]
    > Nota: È inoltre necessario assegnare le autorizzazioni appropriate ai lavoratori, in modo che possano accedere ed eseguire le attività utilizzando il sistema Retail POS.

12. Configurare i profili di Retail POS da assegnare al punto vendita. Questa attività include molte altre attività, ad esempio, l'impostazione dei registratori, dei profili offline oltre che dei formati delle ricevute e dei profili.

Verificare tutte le attività incluse tra i prerequisito e completare solo le attività applicabili alla propria situazione.

### <a name="set-up-a-retail-store"></a>Impostare un punto vendita al dettaglio

Dopo aver completato le attività prerequisite, completare le attività seguenti per impostare i dettagli del punto vendita al dettaglio:

1. Creare un punto vendita al dettaglio.
2. Assegnare una fascia IVA al punto vendita.
3. Assegnare i metodi di pagamento accettati al punto vendita.
4. Aggiungere dettagli alle descrizioni di prodotto per i prodotti offerti che nei punti vendita al dettaglio. Ad esempio, è possibile aggiungere il formato RTF e le immagini. Tali dettagli del prodotto vengono visualizzati in vari contesti, ad esempio sul registratore di cassa POS o nelle etichette stampate.
5. Aggiungere il punto vendita alla gerarchia organizzativa predefinita assegnata a uno scopo di **Assortimento di articoli al dettaglio**, **Rifornimento per vendita al dettaglio** o **Report per vendita al dettaglio**.

### <a name="after-you-set-up-a-retail-store"></a>Dopo aver impostato un punto vendita al dettaglio

Dopo aver immesso i dettagli relativi al punto vendita al dettaglio, completare queste attività per inviare i nuovi dati del punto di vendita al dettaglio a Retail POS.

1. Configurare i registratori di cassa POS per il punto vendita.
2. Assegnare gli assortimenti dei prodotti al punto vendita.
3. Elaborare gli assortimenti per generare l'elenco di prodotti inclusi nell'assortimento e per rendere i prodotti disponibili nel punto vendita al dettaglio.
4. Inviare i dati quali sequenze numeriche, profili hardware e layout delle schermate POS ai registratori di cassa di Retail POS.
5. Pubblicare il punto vendita al dettaglio per inviare i dati del punto vendita a Retail POS.
6. Eseguire i processi per inviare i dati del punto vendita a Retail POS.

## <a name="organization-hierarchies"></a>Gerarchie organizzative

Retail utilizza gerarchie organizzative per strutturare canali di vendita al dettaglio. Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte dell'azienda. Quando si impostano gli archivi, è possibile aggiungerli a una gerarchia organizzativa. I punti vendita, quindi, condividono i dati utilizzati per assortimenti, rifornimento e reporting.

> [!NOTE]
> Per utilizzare la funzionalità di vendita al dettaglio, la chiave di configurazione per **Indirizzi di spedizione multipli**deve essere abilitata. Questa chiave di configurazione è disponibile nelle chiavi **Configurazione commercio** sotto **Amministrazione di sistema**\>**Impostazioni**\>**Configurazione licenza**. Ciò è necessario a causa della funzionalità Retail che esegue varie convalide in base all'indirizzo di consegna configurato a livello di riga ordine cliente.
