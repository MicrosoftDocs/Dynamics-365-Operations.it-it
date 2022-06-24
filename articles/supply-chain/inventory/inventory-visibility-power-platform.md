---
title: App Visibilità dell'inventario
description: Questo articolo descrive come utilizzare l'applicazione Visibilità dell'inventario.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: db158e3b6ae76f69149db04096f99d3dc4251146
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895759"
---
# <a name="use-the-inventory-visibility-app"></a>Utilizzare l'app Inventory Visibility

[!include [banner](../includes/banner.md)]


Questo articolo descrive come utilizzare l'applicazione Visibilità dell'inventario.

Visibilità inventario fornisce un'applicazione guidata dal modello per la visualizzazione. L'applicazione contiene tre pagine: **Configurazione**, **visibilità operativa** e **riepilogo dell'inventario**. Ha le seguenti caratteristiche:

- Fornisce un'interfaccia utente (UI) per la configurazione on-hand e la configurazione soft reservation.
- Supporta le interrogazioni in tempo reale dell'inventario su varie combinazioni di dimensioni.
- Fornisce un'interfaccia utente per pubblicare le richieste di prenotazione.
- Fornisce una visualizzazione personalizzata dell'inventario a disposizione dei prodotti insieme a tutte le dimensioni.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, installare e configurare il componente aggiuntivo Visibilità inventario come descritto in [Installare e configurare Visibilità inventario](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Aprire l'app Visibilità inventario

Per aprire l'app Visibilità inventario, accedere all'ambiente Power Apps e aprire **Visibilità inventario**.

## <a name="configuration"></a><a name="configuration"></a>Configurazione

La pagina **Configurazione** dell'app Visibilità inventario aiuta a impostare la configurazione delle scorte disponibili e la configurazione delle prenotazioni preliminari. Dopo l'installazione del componente aggiuntivo, la configurazione predefinita include un'impostazione predefinita per Microsoft Dynamics 365 Supply Chain Management (l'origine dati `fno`). Potete rivedere l'impostazione predefinita. Successivamente, in base alle esigenze aziendali e ai requisiti di registrazione dell'inventario del sistema esterno, è possibile modificare la configurazione per standardizzare il modo in cui le modifiche all'inventario possono essere registrate, organizzate e interrogate su più sistemi.

Per i dettagli completi su come configurare la soluzione, vedere [Configurare Visibilità inventario](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Visibilità operativa

La pagina di **Visibilità operativa** fornisce i risultati di una query di inventario in tempo reale, basata su varie combinazioni di dimensioni. Quando la funzione *OnHandReservation* è attivata, puoi anche inviare richieste di prenotazione dalla pagina di  **Visibilità operativa** .

### <a name="on-hand-query"></a>Interrogazione a portata di mano

La scheda **Query disponibilità** mostra i risultati di una query di inventario in tempo reale.

Quando selezioni la scheda **Query disponibilità** , il sistema richiede le tue credenziali in modo che possa ottenere il token del portatore che è necessario per interrogare il servizio Visibilità inventario. Potete semplicemente incollare il token del portatore nel campo **BearerToken** e chiudere la finestra di dialogo. Puoi quindi pubblicare una richiesta di ricerca a portata di mano.

Se il token del portatore non è valido, o se è scaduto, devi incollarne uno nuovo nel campo **BearerToken** . Inserisci i valori corretti di **ID cliente**, **ID inquilino**, **Segreto cliente** e poi seleziona **Aggiorna**. Il sistema otterrà automaticamente un nuovo token al portatore valido.

Per pubblicare una query on-hand, inserisci la query nel corpo della richiesta. Usate il modello che è descritto in [Query usando il metodo post](inventory-visibility-api.md#query-with-post-method).

![Impostazioni della query a portata di mano](media/inventory-visibility-query-settings.png "Impostazioni della query a portata di mano")

### <a name="reservation-posting"></a>Prenotazione

Usa la scheda **Prenotazione** per pubblicare una richiesta di prenotazione. Prima di poter pubblicare una richiesta di prenotazione, devi attivare la funzione *OnHandReservation* . Per ulteriori informazioni su questa funzione, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md).

Per pubblicare una richiesta di prenotazione, devi inserire un valore nel corpo della richiesta. Usate il modello che è descritto in [Creare un evento di prenotazione](inventory-visibility-api.md#create-one-reservation-event). Poi seleziona **Registra**. Per visualizzare i dettagli della risposta alla richiesta, selezionare **Mostra dettagli**. È possibile anche ottenere il valore `reservationId` dai dettagli della risposta.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Riassunto dell'inventario

Il **riepilogo dell'inventario** è una vista personalizzata per l'entità *Somma inventario disponibile*. Fornisce un riassunto dell'inventario per i prodotti insieme a tutte le dimensioni. I dati di riepilogo dell'inventario vengono sincronizzati periodicamente da Visibilità inventario ogni 15 minuti. Prima di poter vedere i dati sulla scheda **Riepilogo inventario**, è necessario attivare la funzionalità *OnHandMostSpecificBackgroundService* sulla scheda **Gestione funzionalità** e selezionare **Aggiorna configurazione**.

> [!NOTE]
> La funzionalità *OnHandMostSpecificBackgroundService* tiene traccia solo delle modifiche delle scorte disponibili del prodotto che si sono verificate dopo l'attivazione della funzione. I dati per i prodotti che non sono cambiati da quando hai attivato la funzione non verranno sincronizzati dalla cache del servizio di inventario nell'ambiente Dataverse. Se la pagina **Riepilogo inventario** non mostra tutte le informazioni disponibili che ti aspetti, vai a **Gestione inventario > Attività periodiche > Integrazione visibilità inventario**, disabilita il processo batch e riattivalo. Questo eseguirà il push iniziale e tutti i dati verranno sincronizzati con l'entità *Somma scorte disponibili* nei prossimi 15 minuti. Se desideri utilizzare questa funzione, ti consigliamo di attivarla prima di creare eventuali modifiche alle scorte disponibili e di abilitare il processo batch **Integrazione visibilità inventario**.

Utilizzando il **filtro avanzato** che Dataverse fornisce, è possibile creare una vista personale che mostra le righe importanti per l'utente. Le opzioni di filtro avanzate ti permettono di creare una vasta gamma di visualizzazioni, dalle più semplici alle più complesse. Permettono anche di aggiungere condizioni raggruppate e annidate ai filtri. Per ulteriori informazioni su come utilizzare il **filtro avanzato**, vedere [Modificare o creare viste personali usando i filtri avanzati della griglia](/powerapps/user/grid-filters-advanced).

La parte superiore della vista personalizzata fornisce tre campi: **Dimensione predefinita**, **Dimensione personalizzata** e **Misura**. Puoi usare questi campi per controllare quali colonne sono visibili.

Puoi selezionare l'intestazione della colonna per filtrare o ordinare il risultato corrente.

La parte inferiore della vista personalizzata mostra informazioni come "50 record (29 selezionati)" o "50 record" Questa informazione si riferisce ai record attualmente caricati dal risultato del **filtro avanzato**. Il testo "29 selezionati" si riferisce al numero di record che sono stati selezionati utilizzando il filtro di intestazione della colonna per i record caricati.

Nella parte inferiore della vista c'è un pulsante **Ulteriori informazioni** che puoi usare per caricare altri record da Dataverse. Il numero predefinito di record che viene caricato è 50. Quando si seleziona **Carica altro**, i prossimi 1.000 record disponibili vengono caricati nella vista. Il numero sul pulsante **Carica altro** indica i record attualmente caricati e il numero totale di record per il risultato del **filtro avanzato**.

![Riepilogo scorte](media/inventory-visibility-onhand-list.png "Riepilogo scorte")
