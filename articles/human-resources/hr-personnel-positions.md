---
title: Posizioni
description: Questo argomento descrive gli elementi concettuali che una posizione può includere. Fornisce inoltre esempi che mostrano come utilizzare tali elementi nella propria organizzazione.
author: twheeloc
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bb7582165f49c40d294acd3cf804fe89782936c4
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689440"
---
# <a name="positions"></a>Posizioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive gli elementi concettuali che una posizione può includere. Fornisce inoltre esempi che mostrano come utilizzare tali elementi nella propria organizzazione.

Prima di poter creare una posizione, è necessario impostare una mansione. Alcuni dettagli della posizione come la regione retributiva, l'assegnazione del lavoratore, la durata della posizione e la relazione di reporting sono validi in base alla data.

## <a name="general-information"></a>Informazioni generali

Quando si crea una posizione, è necessario selezionare una mansione. Le seguenti informazioni verranno compilate automaticamente dalla mansione selezionata:

- descrizione
- Funzione
- Equivalente a tempo pieno
- Famiglia di processo

Il titolo della posizione viene utilizzato per fare riferimento al titolo di un dipendente. (Il titolo elencato sul dipendente non viene utilizzato.) Pertanto, i titoli delle posizioni dovrebbero essere standardizzati il più possibile.

> [!NOTE]
> Un lavoratore non può essere assegnato a una posizione in una data precedente alla data di disponibilità per l'assegnazione.
>
> Un parametro nella scheda **Posizioni** della pagina **Parametri condivisi di Human resources** controlla il comportamento dell'assegnazione del lavoratore. Selezionare uno dei seguenti valori:
>
> - **Sempre**: è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni. Quando vengono create posizioni, la data e l'ora **Disponibile per l'assegnazione** nella scheda **Generale** della pagina **Posizione** vengono impostate automaticamente sulla data e ora di creazione.
> - **Mai**: non è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni. Se si seleziona questa opzione, è necessario aprire la pagina **Posizione** per ogni nuova posizione non appena diventa disponibile. Nella scheda **Generale** immettere la data **Disponibile per l'assegnazione** per abilitare l'assegnazione del lavoratore. Se si seleziona questa opzione, l'assegnazione del lavoratore verrà impostato su **Mai** per impostazione predefinita quando si tenta di assegnare il lavoratore.

## <a name="position-duration"></a>Durata posizione

Ogni posizione è valida per un determinato periodo di tempo che viene definito durata. Ad esempio, le posizioni estive possono avere una durata compresa tra il 1 maggio 2021 e il 31 agosto 2021. La data di attivazione è la data in cui la posizione è attiva nel sistema. La data di ritiro è la data in cui la posizione cessa di essere attiva nel sistema.

Si noti che né la data di disponibilità per l'assegnazione né la data di assegnazione del lavoratore possono essere precedenti alla data di attivazione. Una posizione non è considerata attiva finché non viene raggiunta la data di attivazione. Inoltre, l'assegnazione di un lavoratore non può estendersi oltre la data di ritiro della posizione.

## <a name="reports-to-position"></a>Posizione Subordinato a

Le posizioni sono elementi importanti nel livello inferiore di una gerarchia organizzativa. Nella pagina **Posizione** è possibile specificare la posizione subordinata a una posizione. Quando si assegna un lavoratore a una posizione subordinata a un'altra posizione, viene creata una relazione gerarchica tra i lavoratori assegnati alle due posizioni. Ad esempio, la posizione 000220 è subordinata alla posizione 000300. A Kim Akers viene assegnata la posizione 000220 e a Sanjay Patel viene assegnata la posizione 000300. Pertanto, Kim Akers riferisce a Sanjay Patel.

> [!TIP]
> La posizione Subordinato a viene utilizzata in tutto il sistema per determinare chi è il responsabile di un dipendente. Nell'esempio precedente, se il ruolo di responsabile viene assegnato a Sanjay Patel nel sistema, vedrà Kim Akers come subalterno diretto in Responsabile Self-Service. La relazione gerarchica può anche essere utilizzata quando si creano regole di gestione del flusso di lavoro e attività dell'elenco di controllo.

## <a name="relationships"></a>Rapporti

Se l'organizzazione utilizza una gerarchia di matrici o un'altra gerarchia personalizzata, è possibile impostare tipi di gerarchia di posizione. È quindi possibile aggiungere relazioni gerarchighe alle posizioni per ogni tipo di gerarchia impostato. Ad esempio, Lori Penor è una responsabile generale in Adventure Works a cui è stata assegnata la posizione **Responsabile generale**. Lori gestisce lo sviluppo di un prodotto che viene utilizzato per eseguire la pulitura dei congegni meccanici. Ha bisogno di un contabile per la gestione degli aspetti finanziari. Di conseguenza, ha assunto Kim Akers come contabile. Kim risponde direttamente a Sanjay Patel, ma lavora anche con Lori Penor sugli aspetti finanziari per lo sviluppo di un prodotto di pulizia widget.

Per l'esempio precedente, è necessario completate le seguenti attività per impostare la relazione di lavoro tra Kim Akers e Lori Penor:

1. Creare un tipo di gerarchia di posizioni personalizzato denominato **Widget** per creare una gerarchia che includa le posizioni responsabili per le attività sul prodotto di pulizia widget.
2. Specificare la posizione **Responsabile generale** come posizione a cui la posizione di Kim riferisce nella gerarchia **Widget**.
3. Utilizzare la gerarchia di posizioni per visualizzare la struttura gerarchica delle posizioni. Se sono presenti più gerarchie di posizioni, è possibile visualizzare la gerarchia di ogni tipo nella gerarchia di posizioni. È anche possibile cercare una posizione in base all'ID posizione o al nome del lavoratore assegnato alla posizione. La gerarchia di posizioni è una gerarchia organizzativa.

## <a name="labor-union"></a>Sindacato

È possibile registrare se per la posizione è richiesto un contratto sindacale e quale associazione di categoria viene utilizzata. È inoltre possibile associare il contratto a una persona giuridica.

## <a name="financial-dimensions"></a>Dimensioni finanziarie

Quando si crea la dimensione finanziaria per una posizione, è necessario specificare una persona giuridica. È possibile selezionare le dimensioni predefinite per ciascuna dimensione. In alternativa, è possibile selezionare un modello di distribuzione per compilare automaticamente le dimensioni predefinite. Un modello di distribuzione fornisce anche la possibilità di allocare importi tra più valori dimensionali.
