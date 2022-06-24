---
title: Libro contabile di contabilità inventario globale
description: Questo articolo descrive i libri contabili di Contabilità inventario globale, definiti da una combinazione di valuta, calendario, convenzione e associazione con una persona giuridica.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4d3779d7d335a903d7eabfadfed79e47652c6835
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897663"
---
# <a name="global-inventory-accounting-ledger"></a>Libro contabile di contabilità inventario globale

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Contabilità inventario globale ha un proprio set di libri contabili. Ogni volta che viene elaborata una transazione relativa all'inventario per una persona giuridica pertinente, il sistema può contabilizzare tale transazione in qualsiasi numero di libri contabili di Contabilità inventario globale, come richiesto.

Un libro contabile è un registro di misure in Dare e Avere. Queste misure sono classificate utilizzando elementi di costo e conti CoGe secondari. Un libro contabile di Contabilità inventario globale è definito da una combinazione di valuta, calendario, convenzione e associazione con una persona giuridica.

Per impostare i libri contabili di contabilità inventario globale, vai a **Contabilità inventario globale \> Impostazioni \> Libri contabilità inventario globale**. Per ciascun libro imposta i seguenti campi:

- **Nome**: immetti il nome del libro contabile.
- **Descrizione** - Immettere una descrizione del libro contabile.
- **Calendario fiscale** – Specifica il calendario fiscale per il libro contabile.
- **Tipo di tasso di cambio e valuta** – Utilizza i campi di questa Scheda dettaglio per selezionare la valuta contabile utilizzata dal libro contabile e il tipo di tasso di cambio. La valuta selezionata può essere diversa dalla valuta utilizzata dalla persona giuridica. In Contabilità inventario globale, gli utenti possono definire tutti i libri contabili di determinazione dei costi di cui hanno bisogno. Contabilità inventario globale supporta la contabilità inventario in più valute e in più valutazioni. Imposta i seguenti campi:

    - **Valuta** – Seleziona la valuta di determinazione dei costi in cui vengono mantenuti i valori relativi all'inventario. Questi valori includono il valore dell'inventario, il costo delle merci vendute, l'inventario in transito e tutti i tipi di scostamento.
    - **Tipo di tasso di cambio** – Seleziona il tasso di cambio che il sistema deve utilizzare per convertire l'importo della transazione nella valuta di transazione e il costo standard degli articoli nella valuta di determinazione dei costi.

- **Nome convenzione** – Specifica una convenzione. Una convenzione è una raccolta di criteri che stabiliscono come verranno contabilizzati i costi in questo libro contabile.
- **Persona giuridica** – Il libro contabile contabilizzerà i documenti registrati nella persona giuridica selezionata.
- **Preparazione** – Seleziona se le transazioni di inventario create prima della creazione del libro contabile devono essere elaborate in base alla valuta e alla convenzione nel libro contabile. Selezionare uno dei seguenti valori:

    - **Attivato** – Il libro contabile deve elaborare le transazioni create prima della creazione del libro contabile.
    - **Disattivato** – Il libro contabile deve elaborare solo le transazioni create dopo della creazione del libro contabile.

    > [!IMPORTANT]
    > **Non** sarai in grado di tornare indietro e impostare questo campo dopo aver inserito nuovi documenti.

- **Stato** – Il sistema imposta automaticamente lo stato dei libri contati appena creati su *Preparazione*.
