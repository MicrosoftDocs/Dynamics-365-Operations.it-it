---
title: I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico
description: I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924353"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico

Codici di errore: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico %1. Eseguire la verifica della coerenza del peso del carico di magazzino per ricalcolare i campi del peso.

## <a name="cause"></a>Causa

I campi **Peso netto** e **Tara** sono impostati su *0* (zero) sulla riga di carico. Tuttavia, i campi del peso non sono impostati su *0* per le misurazioni del peso nel prodotto. Quando i campi del peso non sono impostati sulla riga di carico, qualsiasi correzione della quantità riga linea di carico potrebbe causare un calcolo del peso errato sul carico. Questo problema potrebbe verificarsi se i pesi del prodotto sono stati modificati dopo la creazione della riga di carico.

## <a name="resolution"></a>Risoluzione

Per impostazione predefinita, quando viene creata una riga di carico, i campi del peso del prodotto vengono inseriti in essa. Se il peso è zero, è possibile ricalcolarlo utilizzando la funzionalità *Verifica coerenza peso carico magazzino*.

1. Selezionare **Amministrazione sistema \> Attività periodiche \> Database \> Verifica coerenza**.
1. Nella finestra di dialogo **Verifica coerenza**, impostare il campo **Modulo** su *Gestione magazzino*.
1. Impostare il campo **Verifica/Correggi** su *Correggi errore*.
1. Nell'elenco delle caselle di controllo, seleziona **Verifica coerenza peso carico magazzino** e assicurati che sia evidenziata solo la riga per questa casella di controllo.
1. Nella parte superiore dell'elenco delle caselle di controllo, seleziona il pulsante con i puntini di sospensione (**...**), quindi seleziona **Finestra di dialogo** sul menu.
1. Nella finestra di dialogo **Verifica coerenza peso carico magazzino** impostare i seguenti campi per specificare i criteri per i quali deve essere eseguita la verifica di coerenza:

    - **ID carico:** Specifica un ID carico. Lascia questo campo vuoto per controllare tutti gli ID carico.
    - **Numero articolo:** Specifica un numero di articolo. Lascia questo campo vuoto per controllare tutti gli articoli.
    - **Ricalcola sempre peso su carichi:** Imposta questa opzione su *Sì*.
    - **Consenti sovrascrittura peso su righe di carico:** Imposta questa opzione su *Sì*.

1. Selezionare **OK** per chiudere la finestra di dialogo **Verifica coerenza peso carico magazzino**.
1. Seleziona il pulsante con i puntini di sospensione e quindi seleziona **Esegui** sul menu.

Il peso viene ricalcolato in base ai criteri specificati. Seleziona il collegamento **Dettagli messaggio** per visualizzare il risultato della verifica di coerenza.
