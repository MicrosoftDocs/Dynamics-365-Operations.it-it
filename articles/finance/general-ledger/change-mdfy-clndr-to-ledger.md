---
title: Modificare o riassegnare un calendario di contabilità generale
description: In questo argomento viene illustrato come modificare il calendario attualmente assegnato alla contabilità generale e come assegnare un nuovo calendario alla contabilità generale.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 25777a5b807921acc13338116627e9356fe62a20
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711633"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Modificare o riassegnare un calendario di contabilità generale

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come modificare il calendario attualmente assegnato alla contabilità generale e come assegnare un nuovo calendario alla contabilità generale.

## <a name="issue"></a>Problema

A volte, le aziende devono modificare il calendario assegnato alla contabilità generale o assegnare un nuovo calendario.

## <a name="resolution"></a>Risoluzione

Sono due gli scenari in cui si modifica o riassegna un calendario di contabilità generale. Il primo scenario prevede la modifica di un calendario esistente già assegnato alla contabilità generale. Il secondo scenario prevede la creazione di un nuovo calendario e l'assegnazione alla contabilità generale. Entrambe le modifiche possono essere apportate in qualsiasi momento, anche dopo che le transazioni sono state registrate nella contabilità generale.

### <a name="change-an-existing-fiscal-calendar"></a>Modificare un calendario fiscale esistente

Per modificare un calendario esistente assegnato alla contabilità generale, andare a **Contabilità generale \> Impostazione contabilità generale \> Contabilità generale** e selezionare il collegamento per il calendario fiscale per aprire la pagina **Calendari contabilità generale**.

Esistono dei limiti alle modifiche che possono essere apportate a un calendario. Ad esempio, è possibile modificare le date di inizio e di fine dei *periodi* in un anno, ma non puoi modificare le date di inizio e fine di un *anno* nel calendario.

Per modificare i periodi di un anno, selezionare il calendario e l'anno appropriati. Per prima cosa, usare il pulsante **Elimina periodo** per eliminare alcuni o tutti i periodi operativi esistenti. Tutti i periodi operativi tranne il primo possono essere eliminati. Quindi usare il pulsante **Dividi periodo** per dividere il periodo o i periodi rimanenti in nuovi periodi, immettendo una data di inizio appropriata per il periodo successivo.

Dopo aver modificato i periodi di un calendario, è necessario eseguire il processo **Ricalcola periodi contabili** in ogni persona giuridica (società) a cui è assegnato il calendario. Sebbene nessun messaggio di avviso ricordi di completare questo passaggio, il processo di ricalcolo è necessario per aggiornare il periodo assegnato a ciascuna transazione registrata nella contabilità generale. Per eseguire il processo di ricalcolo, selezionare **Ricalcola periodi contabili** nella pagina **Impostazione contabilità generale** in ogni società.

Se il processo di ricalcolo non viene eseguito, i saldi delle transazioni in un bilancio di verifica o in un rendiconto finanziario potrebbero essere inclusi in modo errato nei periodi. In questo caso, è possibile correggere i saldi in qualsiasi momento eseguendo il processo di ricalcolo.

### <a name="assign-a-new-fiscal-calendar"></a>Assegnare un nuovo calendario fiscale

Per assegnare un nuovo calendario fiscale, andare a **Contabilità generale \> Impostazione contabilità generale \> Contabilità generale** e selezionare **Modifica** per mettere attivare la modalità di modifica per la pagina **Contabilità generale**. Quindi, nel campo **Calendario fiscale** selezionare un nuovo calendario fiscale.

Dopo aver modificato il calendario fiscale per la contabilità generale, è necessario eseguire **Ricalcola periodi contabili**. Quando si assegna un nuovo calendario fiscale alla contabilità generale, viene visualizzato un messaggio che ricorda di completare questo passaggio. Sebbene il messaggio possa sembrare che indichi che il processo di ricalcolo è facoltativo, non lo è. È necessario aggiornare il periodo assegnato a ciascuna transazione registrata nella contabilità generale. Per eseguire il processo di ricalcolo, selezionare **Ricalcola periodi contabili** nella pagina **Impostazione contabilità generale**.

Se il processo di ricalcolo non viene eseguito, i saldi delle transazioni in un bilancio di verifica o in un rendiconto finanziario potrebbero essere inclusi in modo errato nei periodi. In questo caso, è possibile correggere i saldi in qualsiasi momento eseguendo il processo di ricalcolo.
