---
title: Utilizzo di Power Portal con il modello di dati parte
description: In questo argomento vengono descritte le modifiche ai ruoli Web di Power Portal a causa del modello di dati della parte in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833092"
---
# <a name="using-power-portal-with-the-party-data-model"></a>Utilizzo di Power Portal con il modello di dati parte

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

La versione della soluzione di orchestrazione delle applicazioni a doppia scrittura 2.0.999.0 e successive include le modifiche al modello di dati della parte e alla rubrica globale per le tabelle Conto e Contatto. Le modifiche consentono le relazioni molti-a-molti che supportano scenari aziendali avanzati. Queste modifiche non sono supportate dai ruoli Web del portale, incluso il portale del cliente, forniti in modo predefinito o esistenti nell'ambiente prima dell'installazione della doppia scrittura. Affinché i ruoli Web funzionino come previsto, è necessario creare nuovi ruoli Web utilizzando il nuovo modello di dati. 

In sintesi, il modo in cui le tabelle interagiscono è cambiato, ma le autorizzazioni delle tabelle nel portale dei clienti non sono cambiate. Questo argomento spiega come creare nuovi ruoli Web che funzionano con il nuovo modello di dati avanzato.

Questo diagramma mostra la relazione tra le tabelle **senza** il modello dei dati la parte e della rubrica globale:

   ![senza modello di parte](media/without-party-model.PNG)

Questo diagramma mostra la relazione tra le tabelle **con** il modello dei dati la parte e della rubrica globale:

   ![con il modello di parte](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Creare una nuova autorizzazione per la tabella

Per creare queste nuove autorizzazioni per la tabella, segui questi passaggi:

1. Accedi a [Power Apps](https://make.powerapps.com) e vai alle tue app.
2. Seleziona la tua app di gestione del portale.
3. Nella barra laterale, seleziona **Sicurezza > Autorizzazioni tabella**.

    Devi creare tre nuove autorizzazioni:

    + Connessione da contatto a parte
    + Connessione da parte a conto
    + Connessione da conto a ordine

4. Crea e salva una nuova autorizzazione per la connessione da contatto a parte, impostando questi parametri:

    + **Nome**: Connessione da parte a conto (o a tua scelta)
    + **Nome tabella**: msdyn_contactforparty
    + **Sito Web**: portale del cliente
    + **Ambito**: Contatto
    + **Privilegi**: Seleziona tutto
    + **Ruoli Web**: Utenti autenticati, rappresentante clienti (o a scelta)

5. Crea e salva una nuova autorizzazione per la connessione da parte a conto, impostando questi parametri:

    + **Nome**: Connessione da parte a conto (o a tua scelta)
    + **Nome tabella**: conto
    + **Sito Web**: portale del cliente
    + **Ambito**: padre
    + **Privilegi**: Seleziona tutto
    + **Autorizzazione tabella padre**: connessione da contatto a parte

6. Crea e salva una nuova autorizzazione per la connessione da conto a ordine, impostando questi parametri:

    + **Nome**: Connessione da conto a ordine (o a tua scelta)
    + **Nome tabella**: ordine cliente
    + **Sito Web**: portale del cliente
    + **Ambito**: padre
    + **Privilegi**: Seleziona tutto
    + **Autorizzazione tabella padre**: connessione da parte a conto

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
