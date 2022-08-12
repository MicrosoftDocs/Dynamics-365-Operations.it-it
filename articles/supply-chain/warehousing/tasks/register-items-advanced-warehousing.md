---
title: Registrare articoli abilitati per i processi di gestione del magazzino tramite un giornale di registrazione arrivi articoli
description: Questo articolo presenta uno scenario che mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizzano i processi di gestione del magazzino (WMS).
author: Mirzaab
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5241c982675d6b9a9bc9596b8ac9ed2798903287
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066969"
---
# <a name="register-items-enabled-for-warehouse-management-processes-using-an-item-arrival-journal"></a>Registrare articoli abilitati per i processi di gestione del magazzino tramite un giornale di registrazione arrivi articoli

[!include [banner](../../includes/banner.md)]

Questo articolo presenta uno scenario che mostra come registrare gli articoli utilizzando il giornale di registrazione arrivi articoli quando si utilizzano i processi di gestione del magazzino (WMS). Questa operazione viene generalmente effettuata da un addetto al ricevimento.

## <a name="enable-sample-data"></a>Abilitare dati di esempio

Per gestire questo scenario utilizzando i record e i valori di esempio specificati in questo articolo, è necessario utilizzare un sistema in cui sono installati i dati demo standard ed è necessario selezionare la persona giuridica *USMF* prima di iniziare.

Puoi invece elaborare questo scenario sostituendo i valori dei tuoi dati a condizione che tu abbia i seguenti dati disponibili:

- Devi avere un ordine cliebte confermato con una riga dell'ordine fornitore aperta.
- L'articolo nella riga deve essere stoccato. Non deve utilizzare varianti di prodotto e non deve avere dimensioni di tracciabilità.
- L'articolo deve essere associato a un gruppo di dimensioni di immagazzinamento con un processo di gestione magazzino abilitato.
- Il magazzino utilizzato deve essere abilitato per WMS e l'ubicazione utilizzata per il ricevimento deve essere controllata da targa.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Creare un'intestazione del giornale di registrazione arrivi articoli che utilizzi la gestione di magazzino

Lo scenario seguente mostra come creare un'intestazione del giornale di registrazione arrivi articoli che utilizza la gestione magazzino:

1. Assicurati che il tuo sistema contenga un ordine fornitore confermato che soddisfi i requisiti descritti nella sezione precedente. Questo scenario utilizza un ordine fornitore per la società *USMF*, account fornitore *1001*, magazzino *51*, con una riga d'ordine per *10 PL* (10 pallet) del numero di articolo *M9200*.
1. Prendi nota del numero di ordine fornitore che userai.
1. Vai a **Gestione articoli \> Inserimenti nel giornale di registrazione \> Arrivo articoli \> Arrivo articoli**.
1. Nel Riquadro azioni seleziona **Nuovo**.
1. Si apre la finestra di dialogo **Crea giornale di registrazione gestione inventario**. Seleziona un nome del giornale di registrazione nel campo **Nome**.
    - Se utilizzi i dati di esempio *USMF* seleziona *WHS*.
    - Se stai usando i tuoi dati, il giornale di registrazione che scegli deve avere **Verifica ubicazione prelievo** impostato su *No* e **Gestione quarantena** impostato su *No*.
1. Imposta **Riferimento** su *Ordine fornitore*.
1. Imposta **Numero conto** su *1001*.
1. Imposta **Numero** sul numero dell'ordine fornitore che hai identificato per questo esercizio.

    ![Giornale di registrazione arrivi articoli.](../media/item-arrival-journal-header.png "Giornale di registrazione arrivi articoli")

1. Seleziona **OK** per creare l'intestazione del giornale di registrazione.
1. Nella sezione **Righe giornale di registrazione** seleziona **Aggiungi riga** e inserisci i seguenti dati:
    - **Numero articolo** - Imposta su *M9200*. I campi **Sito**, **Magazzino** e **Quantità** verranno impostati in base ai dati della transazione di inventario per i 10 pallet (1000 cad.).
    - **Ubicazione** - Imposta su *001*. Questa ubicazione specifica non tiene traccia delle targhe.

    ![Riga del giornale di registrazione arrivi articoli.](../media/item-arrival-journal-line.png "Riga del giornale di registrazione arrivi articoli")

    > [!NOTE]
    > Il campo **Data** determina la data in cui la quantità disponibile dell'articolo verrà registrata in magazzino.  
    >
    > L'**ID lotto** sarà popolato dal sistema se può essere identificato in modo univoco dalle informazioni fornite. Altrimenti sarà necessario immetterlo manualmente. Questo è un campo obbligatorio, che collega la registrazione a una riga specifica del documento di origine.  

1. Nel riquadro azioni, seleziona **Convalida**. Ciò verifica che il giornale di registrazione è pronto per essere registrato. Se la convalida ha esito negativo sarà necessario correggere gli errori prima di registrare il giornale di registrazione.  
1. Si apre la finestra di dialogo **Verifica giornale di registrazione**. Selezionare **OK**.
1. Esamina la barra dei messaggi. Dovrebbe esserci un messaggio che indica che l'operazione è stata completata.  
1. Nel riquadro azioni seleziona **Registra**.
1. Si apre la finestra di dialogo **Registra giornale**. Selezionare **OK**.
1. Esamina la barra dei messaggi. Dovrebbe esserci un messaggio che indica che l'operazione è stata completata.
1. Seleziona **Funzioni > Entrata prodotti** nel riquadro azioni per aggiornare la riga dell'ordine fornitore e registrare un'entrata prodotti.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
