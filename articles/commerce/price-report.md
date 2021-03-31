---
title: Report dei prezzi di vendita al dettaglio
description: In questo argomento viene fornita una panoramica della funzionalità di report dei prezzi che può essere utilizzata per visualizzare le future modifiche dei prezzi per i prodotti assortiti.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: f317b22f2794dc71093068a51c8e9d4e6d7d55ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231154"
---
# <a name="retail-price-reports"></a>Report dei prezzi di vendita al dettaglio

[!include [banner](includes/banner.md)]


Per fornire prezzi concorrenziali ai clienti, i rivenditori spesso modificano i prezzi dei prodotti. I responsabili punto vendita vogliono avere la possibilità di accedere facilmente alle modifiche recenti o future dei prezzi in modo da poter pianificare le risorse necessarie per aggiornare le etichette dei prezzi visualizzate sugli scaffali del punto vendita. Con Retail versione 10.0, un responsabile punto vendita può aprire il report **Prezzi** accedendo a **Tutti i punti vendita \> Punto vendita \> Report prezzi** e visualizzando i prezzi aggiornati per i prodotti associati al punto vendita. 

Per abilitare il report dei prezzi, il parametro **Abilita report prezzi per punto vendita** deve essere attivato. Questo parametro si trova nella scheda **Parametri di commercio \> Sconti \> Varie**. L'apertura della pagina **Report prezzi** visualizza una finestra di dialogo con varie configurazioni. Le configurazioni disponibili sono elencate di seguito.

| Configurazione | Descrizione |
|---|---|
| Dal / Al| L'intervallo di date per il quale il report dei prezzi deve essere generato. La durata è attualmente limitata a 7 giorni. |
| Canale| Il punto vendita per il quale il report dei prezzi deve essere generato. |
| Visualizza prodotti con scorte disponibili| Impostando questa opzione su **Sì**, verranno visualizzati i prezzi soltanto per i prodotti per i quali l'inventario fisico è disponibile nel punto vendita. |
| Visualizza prezzi per varianti | L'impostazione di questa opzione su **Sì** visualizzerà i prezzi delle varianti insieme alle rappresentazioni generali prodotto. Questa opzione deve essere **attivata** solo se i prezzi sono specifici alle varianti, in quanto il numero di righe diventa molto grande. Nelle versioni future, verranno abilitati i prezzi basati su dimensioni di modo che il responsabile punto vendita possa scegliere le dimensioni per le quali i prezzi devono essere visualizzati. |
| Visualizza prodotti con variazioni di prezzo | L'impostazione di questa opzione su **Sì** visualizzerà i prezzi solo per le date in cui il prezzo è stato modificato. Il prezzo di *un giorno prima* della **data iniziale** selezionata verrà sempre visualizzato, di modo che il responsabile punto vendita possa facilmente identificare i prodotti senza prezzi modificati per l'intera durata selezionata nonché visualizzare il prezzo corrente. |

Dopo la generazione del report, il file di Excel può essere scaricato per tutti i requisiti di filtro aggiuntivi. Il report dei prezzi può essere utilizzato per verificare i prezzi storici dei prodotti per le date passate.


[!INCLUDE[footer-include](../includes/footer-banner.md)]