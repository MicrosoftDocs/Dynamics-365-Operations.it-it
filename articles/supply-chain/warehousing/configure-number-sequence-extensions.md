---
title: Configurare sequenze numeriche per flussi di magazzino
description: Questo argomento fornisce una panoramica della funzionalità che fornisce estensioni di sequenza numerica per ID targa, ID etichetta ondata, ID contenitore e ID polizza di carico.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: configure-number-sequence-extensions
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExtension
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 2f4506d2c1808198d4b10e50f4635bcc21d934e1
ms.sourcegitcommit: 0f877ee4b53cfb002b179a53a67c4f9adae354bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "3640401"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Configurare sequenze numeriche per flussi di magazzino

[!include [banner](../includes/banner.md)]

La funzionalità *Estensioni di sequenza numerica* aggiunge una nuova pagina di configurazione per l'impostazione di sequenze numeriche. Consente la configurazione flessibile di ID regolati da GS1, inclusi prefissi GS1 e cifre di controllo (modulo 10), e applica un limite di lunghezza sulle sequenze numeriche esistenti.

I segmenti di sequenza numerica standard non sono adatti per l'implementazione GS1, poiché non viene calcolata alcuna cifra di controllo e il prefisso GS1 dell'azienda deve essere aggiornato manualmente.

Questa soluzione aggiunge le seguenti funzionalità:

- Gli ID polizza di carico possono essere generati in anticipo.
- È possibile generare una sequenza numerica univoca per i numeri SSCC.
- È possibile creare sequenze numeriche conformi a GS1 per numeri di polizza di carico e SSCC. La funzionalità aggiunge supporto predefinito per ID targa, ID contenitore, ID etichetta ondata e ID polizza di carico.
- La configurazione dei numeri ID targa è flessibile. Ad esempio, è possibile includere o escludere gli identificatori dell'applicazione, come gli zeri iniziali (00).

Questa funzionalità rende più efficiente il supporto dell'etichettatura di cartoni e la regolazione di nuovi numeri generati dal sistema.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Attivare la funzionalità Estensioni di sequenza numerica

Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Estensioni di sequenza numerica*

## <a name="set-up-the-feature"></a>Configurare la funzionalità

Per configurare le estensioni di sequenza numerica nel sistema, attenersi alla seguente procedura.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale**, nel campo **Prefisso società GS1** immettere il prefisso GS1 della propria società. Questo valore influirà su tutte le sequenze numeriche in cui il prefisso GS1 è incluso come segmento.
1. Se si desidera generare numeri di polizza di carico per etichette ondata, nella scheda **Report**, selezionare la casella di controllo **Genera numero polizza di carico quando si stampano etichette ondata**.

    > [!NOTE]
    > Questa casella di controllo è disponibile solo se la funzionalità per la [stampa di etichette ondata](configure-wave-label-printing.md) è attivata.

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Estensioni di sequenza numerica**
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**. Vengono creati una sequenza numerica di polizze di carico conforme a GS1 e tre tipi di sequenze numeriche SSCC. Tutte queste sequenze numeriche tengono conto della lunghezza del prefisso GS1 della società.

    Per ulteriori informazioni su come personalizzare queste sequenze numeriche predefinite e/o aggiungere nuove sequenze, vedere la sezione successiva. È anche possibile rimuovere una di queste sequenze se non è necessaria.

1. Ritornare **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Sequenze numeriche**, selezionare un'estensione di sequenza numerica pertinente da utilizzare per generare numeri per ID targa, ID etichetta ondata, ID contenitore (in questo caso, selezionare la sequenza **Numero SSCC-18** appropriata) e/o ID polizza di carico (in questo caso, selezionare la sequenza **Polizza di carico**). Per impostazione predefinita, le estensioni di sequenza numerica sono supportate solo per questi quattro tipi di ID.

La prossima volta che viene generato un nuovo numero per una di queste sequenze numeriche, verrà utilizzata la nuova logica.

> [!NOTE]
> Se non si seleziona un'estensione di sequenza numerica per gli ID targa, verranno utilizzate le regole correnti per la generazione di ID targa. Altrimenti, verrà utilizzata la sequenza numerica selezionata. Gli altri ID useranno una sequenza numerica semplice fino a quando non si applica un'estensione di sequenza numerica per tali ID.

## <a name="create-and-edit-number-sequences"></a>Creare e modificare sequenze numeriche

Nella sezione precedente, è stato generato un set predefinito di sequenze numeriche. Questa sezione spiega come viene definita ciascuna sequenza numerica. Descrive inoltre come creare sequenze personalizzate e come modificare le sequenze predefinite o personalizzate.

Per creare e modificare sequenze numeriche, attenersi alla seguente procedura.

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Estensioni di sequenza numerica**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Estensione di sequenza numerica**, immettere un nome per la nuova sequenza. Nel campo **Descrizione** immettere una descrizione.
1. Nella Scheda dettaglio **Segmenti**, utilizzare i pulsanti sulla barra degli strumenti per assemblare il formato di numerazione aggiungendo, eliminando e disponendo i segmenti. Nel campo **Segmento** di ogni riga, assegnare un tipo di segmento per definire lo scopo e il contenuto di quel segmento. Nella seguente tabella vengono illustrati i tipi di segmenti disponibili.

    | Tipo di segmento | descrizione |
    |---|---|
    | Costante | Questo tipo di segmento aggiunge lo stesso testo costante per ciascun numero generato nella sequenza. Nel campo **Valore** immettere il testo necessario. Il campo **Lunghezza** viene automaticamente aggiornato alla lunghezza del testo immesso nel campo **Valore**. |
    | Sequenza numerica | Nel campo **Valore** immettere un segno numerico (*\#*) per ogni carattere che dovrebbe essere mostrato nella sequenza generata. La sequenza numerica stessa potrebbe generare numeri più lunghi, ma verranno visualizzati solo i caratteri più a destra. Il campo **Lunghezza** viene automaticamente aggiornato al numero di segni numerici immessi nel campo **Valore**.<p>Per soddisfare i requisiti GS1 per i numeri SSCC-18, assicurarsi che la lunghezza di questo segmento sia 16 meno la lunghezza del prefisso GS1.</p> |
    | Prefisso GS1 | Questo tipo di segmento aggiunge il valore impostato nel campo **Prefisso società GS1** alla pagina **Parametri di gestione magazzino**. Il campo **Valore** mostra il valore impostato nella **Parametri di gestione magazzino** e il campo **Lunghezza** mostra il numero di caratteri nel valore. Il campo **Valore** e il campo **Lunghezza** sono entrambi di sola lettura. |
    | Identificatore applicazione | Nel campo **Valore**, immettere un identificatore dell'applicazione, come specificato dai criteri GS1 pertinenti per questo tipo di sequenza numerica. Ad esempio, immettere *00* per SSCC o *420* per Polizza di carico. Il campo **Lunghezza** viene automaticamente aggiornato alla lunghezza dell'identificatore immesso nel campo **Valore**. |
    | Tipo di imballaggio | Per gli articoli che possono essere chiaramente identificati, questo tipo di segmento aggiunge un valore di campo dal relativo gruppo di sequenze unità (nella pagina **Gruppi di sequenze unità**) (questo comportamento corrisponde alla logica esistente per gli ID targa). Per le targhe che includono più unità di stockkeeping (SKU), questo tipo di segmento aggiunge *0* (zero) per impostazione predefinita. Per questo tipo di segmento, il campo **Valore** è sempre impostato su *P* e il campo **Lunghezza** è sempre impostato su *1*.|
    | Cifra di controllo | Questo tipo di segmento aggiunge una cifra di controllo, che è un calcolo del modulo 10 (questo comportamento corrisponde alla logica esistente per gli ID targa). Per questo tipo di segmento, il campo **Valore** è sempre impostato su un accento circonflesso (*^*) e il campo **Lunghezza** è sempre impostato su *1*. |

1. Per visualizzare un esempio del formato numerico finale, controllare il campo **Formato** nella parte inferiore della Scheda dettaglio **Segmenti**.
