---
title: Definire le regole di copertura per gli articoli
description: Questa procedura mostra come creare le regole di copertura e ignorare le impostazioni di copertura per un articolo specifico. Viene inoltre illustrato come specificare le impostazioni predefinite di magazzino.
author: t-benebo
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bca0e1786adb08a7cd4795b49c974ab95183b1dd
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469324"
---
# <a name="define-coverage-rules-for-items"></a>Definire le regole di copertura per gli articoli

[!include [banner](../../includes/banner.md)]

La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura mostra come creare le regole di copertura e ignorare le impostazioni di copertura per un articolo specifico. Viene inoltre illustrato come specificare le impostazioni predefinite di magazzino.

## <a name="create-a-coverage-group"></a>Creare un gruppo di copertura

Creare un gruppo di copertura effettuando le seguenti operazioni:

1. Passare a **Pannello di navigazione > Moduli > Pianificazione generale > Impostazioni > Gruppi di copertura**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Gruppo di copertura**.
1. Digitare un valore nel campo **Nome**.
1. Digitare un valore nel campo **Calendario**. Selezionare il calendario utilizzato dalla pianificazione generale per creare i suggerimenti di rifornimento per gli articoli inclusi nel gruppo.  
1. Nel campo **Codice copertura** selezionare un'opzione. Selezionare 'Fabbisogno' per questa procedura.  
1. Nel campo **Intervallo temporale di copertura (giorni)** immettere '90'. Per gli articoli inclusi nel gruppo, la pianificazione generale creerà i suggerimenti di rifornimento per i fino a 90 giorni nel futuro.  
1. Nel campo **Giorni negativi** immettere '1'.
1. Nel campo **Giorni positività** immettere '1'.
1. Espandere o comprimere la sezione **Altro**.
1. Nella sezione **Margini di sicurezza in giorni**, nel campo **Margine su entrata in magazzino aggiunto dalla data del fabbisogno**, immettere '1'. Ad esempio, se il margine sull'entrata in magazzino è impostato su 1 giorno e una riga ordine fornitore è programmata per l'entrata il 15 maggio, la programmazione generale calcola come data di entrata rettificata il giorno 16 maggio.
1. Nel campo **Margine su uscita da magazzino detratto dalla data del fabbisogno** immettere '1'. Ad esempio, se il margine di sicurezza è impostato su 1 giorno e una riga ordine cliente è programmata per la consegna il 15 maggio, la programmazione generale calcola come data rettificata il giorno 14 maggio.  
1. Nel campo **Margine di riordino aggiunto al lead time dell'articolo** immettere '1'.
1. Selezionare **Salva**.

## <a name="create-a-new-product"></a>Crea un nuovo prodotto

Creare un nuovo prodotto effettuando le seguenti operazioni:

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
1. Selezionare **Nuovo**.
1. Nel campo **Numero prodotto**, digitare un valore.
1. Digitare un valore nel campo **Nome prodotto**.
1. Nel campo **Gruppo di modelli di articoli** fare clic sul pulsante a discesa per aprire la ricerca.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Nel campo **Gruppo di articoli** fare clic sul pulsante a discesa per aprire la ricerca.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Nel campo **Gruppo di dimensioni di immagazzinamento** selezionare il pulsante a discesa per aprire la ricerca.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Selezionare **OK**.

## <a name="set-up-default-order-settings"></a>Configurare impostazioni ordine predefinite

Configurare impostazioni ordine predefinite effettuando le seguenti operazioni:

1. Nel **riquadro Azioni**, selezionare **Pianifica**.
1. In **Impostazioni ordine**, selezionare **Impostazioni ordine predefinite**.
1. In **Ordine fornitore**, nel campo **Sito predefinito**, immettere il sito utilizzato come predefinito quando vengono creati gli ordini fornitore.
1. Nel campo **Magazzino predefinito** immettere il sito in cui è immagazzinato l'articolo.
1. Espandere o comprimere la sezione **Inventario**.
1. Nel campo **Multiplo** digitare '10'.
1. Nel campo **Quantità min. ordine**, immettere '10'.
1. Nel campo **Quantità max. ordine**, immettere '100'.
1. Nel campo **Quantità ordine standard**, immettere '10'.
1. Nel campo **Lead time acquisto** immettere un numero.
1. Selezionare o deselezionare la casella di controllo **Giorni lavorativi**.
1. Selezionare **Salva**.
1. Nel campo **Tipo di ordine predefinito** selezionare 'Ordine fornitore'.
1. Selezionare **Salva**.
1. Chiudere la pagina. Chiudere la pagina Impostazioni ordine predefinite.  

## <a name="add-an-item-to-a-coverage-group"></a>Aggiunge un articolo a un gruppo di copertura

Aggiungere un articolo a un gruppo di copertura effettuando le seguenti operazioni:

1. Espandere o comprimere la sezione **Piano**.
1. Nel campo **Gruppo di copertura**, selezionare il pulsante a discesa per aprire la ricerca.
1. Nell'elenco, individuare il **gruppo di copertura** creato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="create-item-coverage-rules"></a>Crea le regole copertura articoli

Creare regole copertura articoli effettuando le seguenti operazioni:

1. Nel **riquadro Azioni**, selezionare **Pianifica**.
1. In **Copertura**, selezionare **Copertura articoli**.
1. Selezionare **Nuovo**.
1. Selezionare la scheda **Generale**.
1. Selezionare la casella nell'intestazione di **Ignora impostazioni gruppo di copertura**.
1. Nel campo **Intervallo temporale di copertura (giorni)** immettere '60'. Anche se gli articoli nel gruppo di copertura Fabbisogno sono pianificati 90 giorni in anticipo, l'articolo verrà pianificato 60 giorni in anticipo.  
1. Nel campo **Giorni negativi** immettere '2'.
1. Nel campo **Giorni positività** immettere '2'.
1. Selezionare la scheda **Lead time**.
1. Selezionare la casella sull'intestazione di **Acquisto**.
1. Nel campo **Ora dell'acquisto** immettere '5'.
1. Seleziona **Salva**.

> [!NOTE]
> Per gli articoli prodotti, il **Lead time di produzione** viene utilizzato se non esiste un ciclo di lavorazione per l'articolo. Se all'articolo è stato associato un ciclo di lavorazione attivo, la pianificazione generale pianificherà l'ordine e ne calcolerà le date in base ai tempi del ciclo di lavorazione e alla capacità delle risorse (se applicabile).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
