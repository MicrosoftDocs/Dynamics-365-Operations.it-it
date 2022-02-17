---
title: Utilizzo dei portali Microsoft Power Apps con il modello di dati parte
description: In questo argomento vengono descritte le modifiche ai ruoli Web dei portali Microsoft Power Apps a causa del modello di dati della parte in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8242a74b8b2251a8489b772f5c4746b113fe2987
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060922"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>Utilizzo dei portali Microsoft Power Apps con il modello di dati parte

[!INCLUDE[banner](../../includes/banner.md)]



La versione della soluzione di orchestrazione delle applicazioni a doppia scrittura 2.0.999.0 e successive include le modifiche al modello di dati della parte e alla rubrica globale per le tabelle Conto e Contatto. Le modifiche consentono le relazioni molti-a-molti che supportano scenari aziendali avanzati. Queste modifiche non sono supportate dai ruoli Web del portale, incluso il portale del cliente, forniti in modo predefinito o esistenti nell'ambiente prima dell'installazione della doppia scrittura. Affinché i ruoli Web funzionino come previsto, è necessario creare nuovi ruoli Web utilizzando il nuovo modello di dati. 

In sintesi, il modo in cui le tabelle interagiscono è cambiato, ma le autorizzazioni delle tabelle nel portale dei clienti non sono cambiate. Questo argomento spiega come creare nuovi ruoli Web che funzionano con il nuovo modello di dati avanzato.

Questo diagramma mostra la relazione tra le tabelle **senza** il modello dei dati la parte e della rubrica globale:

   ![senza modello di parte.](media/without-party-model.PNG)

Questo diagramma mostra la relazione tra le tabelle **con** il modello dei dati la parte e della rubrica globale:

   ![con modello di parte.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Creare una nuova autorizzazione per la tabella

Per creare queste nuove autorizzazioni per la tabella, segui questi passaggi:

1. Accedi a [Power Apps](https://make.powerapps.com) e vai alle tue app.
2. Seleziona la tua app di gestione del portale.
3. Nella barra laterale, seleziona **Sicurezza > Autorizzazioni tabella**.

    Devi creare tre nuove autorizzazioni:

    + Connessione della tabella da **Contatto** a **Parte**
    + Connessione della tabella da **Parte** a **Conto**
    + Connessione della tabella da **Conto** a **Ordine**

4. Crea e salva una nuova autorizzazione per la connessione da contatto a parte, impostando questi parametri:

    + **Nome**: Connessione della tabella da **Parte** a **Conto** (o la tua scelta)
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
