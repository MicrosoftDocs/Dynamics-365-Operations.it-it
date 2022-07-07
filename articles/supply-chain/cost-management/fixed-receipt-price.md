---
title: Prezzo di entrata fisso
description: Questo articolo spiega come configurare e utilizzare i prezzi di entrata fissi in Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: d58e8dcc580bf9327cd89427530f59340e27f4aa
ms.sourcegitcommit: 78576abe5c7cbab1bb69d26c999b038e8c24873a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954694"
---
# <a name="fixed-receipt-price"></a>Prezzo di entrata fisso

[!include [banner](../includes/banner.md)]

**Prezzo di entrata fisso** è un'opzione che puoi selezionare su un gruppo di modelli di articoli quando utilizzi un modello di inventario diverso da *Costo standard* o *Media ponderata mobile*. Nelle prime versioni di Microsoft Dynamics AX, questa opzione era denominata **Costo standard**. È stata rinominata **Prezzo di entrata fisso** quando il nuovo modello di inventario a costo standard è stato introdotto in Dynamics AX 2012. Questo articolo spiega come configurare e utilizzare i prezzi di entrata fissi in Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>Informazioni sui prezzi di entrata fissi

Quando selezioni la casella di controllo **Prezzo di entrata fisso** sulla pagina **Gruppo di modelli di articoli** per un articolo, il sistema utilizza il prezzo di entrata come costo standard per l'entrata inventario. Se c'è una differenza tra il prezzo di acquisto e il prezzo di costo articolo predefinito configurato per un prodotto, la differenza verrà registrata nel conto **Profitto sul prezzo di entrata fisso** o **Perdita sul prezzo di entrata fisso** e compensa nel conto **Deviazione prezzo di entrata fisso** specificato nella pagina **Profilo di registrazione dell'inventario**.

Perché l'opzione **Prezzo di entrata fisso** viene utilizzata insieme a diversi modelli di inventario (come first in, first out (FIFO), last in, first out (LIFO) e media ponderata), il processo *Chiusura e rettifica dell'inventario* creerà comunque liquidazioni e rettifiche in base al principio di inventario selezionato nella pagina **Gruppo di modelli di articoli**. Tuttavia, le rettifiche vengono apportate solo alle uscite dall'inventario.

Ad esempio, hai configurato un prodotto con un gruppo di modelli di articoli in cui il campo **Modello di inventario** è impostato su *FIFO* e l'opzione **Prezzo di entrata fisso** è selezionata. Quando ricevi l'inventario tramite un ordine fornitore, il valore dell'inventario viene impostato sul valore del prezzo di costo predefinito dell'articolo al momento dell'entrata del prodotto. Quando fatturi l'ordine fornitore, se il prezzo della fattura è diverso, il sistema registra il prezzo di costo predefinito del prodotto rilasciato nel conto inventario. Registra la differenza nel conto profitti o perdite del prezzo di entrata fisso. Successivamente, quando vendi o consumi il prodotto, il sistema utilizza la media corrente per l'articolo nel momento in cui è stata registrata la fattura dell'ordine cliente (a meno che non si utilizzi il contrassegno).

Quando esegui il processo *Chiusura e rettifica dell'inventario*, il sistema crea una liquidazione con la prima uscita rispetto alla prima entrata. La differenza tra il prezzo di entrata utilizzato all'entrata e la media corrente utilizzata all'uscita viene registrata in un nuovo giustificativo.

## <a name="enable-fixed-receipt-prices"></a>Abilitare i prezzi di entrata fissi

Per abilitare i prezzi di entrata fissi per un articolo, attieniti alla seguente procedura.

1. Andare a **Gestione articoli \> Impostazioni \> Scorte \> Gruppi di modelli di articoli**.
2. Crea un nuovo gruppo di modelli di articoli o seleziona un gruppo di modelli esistente.
3. Sulla Scheda dettaglio **Metodo di determinazione dei costi e riconoscimento dei costi** seleziona la casella di controllo **Prezzo di entrata fisso**.

    > [!NOTE]
    > Non puoi selezionare la casella di controllo **Prezzo di entrata fisso** se il campo **Modello di inventario** è impostato su *Costo standard* o *Media mobile*.

4. Chiudi la pagina.

Dopo aver abilitato l'opzione **Prezzo di entrata fisso** è necessario aggiornare il profilo di registrazione dell'inventario seguendo questi passaggi.

1. Vai a **Gestione scorte \> Impostazione \> Registrazione \> Registrazione**.
1. Sulla scheda **Ordine fornitore** nella colonna **Seleziona** seleziona **Profitto prezzo di entrata fisso**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Imposta la nuova riga in modo che si applichi al gruppo di modelli di articolo per cui hai abilitato il prezzo di entrata fisso e specifica il conto principale utilizzato per registrare i profitti del prezzo di entrata fisso per gli ordini fornitore. Configura altre impostazioni come richiesto.
1. Nella colonna **Seleziona** seleziona **Perdita prezzo di entrata fisso**. Aggiungi una nuova riga in modo che si applichi al gruppo di modelli di articolo per cui hai abilitato il prezzo di entrata fisso e specifica il conto principale utilizzato per registrare le perdite del prezzo di entrata fisso per gli ordini fornitore. Configura altre impostazioni come richiesto.
1. Nella colonna **Seleziona** seleziona **Deviazione prezzo di entrata fisso**. Aggiungi una nuova riga in modo che si applichi al gruppo di modelli di articolo per cui hai abilitato il prezzo di entrata fisso e specifica il conto principale utilizzato per registrare le deviazioni del prezzo di entrata fisso per gli ordini fornitore. Configura altre impostazioni come richiesto.
1. Sulla scheda **Inventario** nella colonna **Seleziona** seleziona **Profitto prezzo di entrata fisso**. Aggiungi una nuova riga in modo che si applichi al gruppo di modelli di articolo per cui hai abilitato il prezzo di entrata fisso e specifica il conto principale utilizzato per registrare i profitti del prezzo di entrata fisso per l'inventario. Configura altre impostazioni come richiesto.
1. Nella colonna **Seleziona** seleziona **Perdita prezzo di entrata fisso**. Aggiungi una nuova riga in modo che si applichi al gruppo di modelli di articolo per cui hai abilitato il prezzo di entrata fisso e specifica il conto principale utilizzato per registrare le perdite del prezzo di entrata fisso per l'inventario. Configura altre impostazioni come richiesto.

> [!NOTE]
> Di solito consigliamo che i campi **Profitto del prezzo di entrata fisso** e **Perdita del prezzo di entrata fisso** utilizzino lo stesso account principale sia per gli ordini fornitore che per l'inventario.

> [!IMPORTANT]
> Quando modifichi il valore nel campo **Prezzo** sulla scheda dettagli **Gestione costi** della pagina **Prodotti rilasciati**, il sistema non rivaluta automaticamente l'inventario disponibile. Come soluzione manuale, apri la pagina **Chiusura e rettifica** e seleziona **Rettifica \> Scorte disponibili** nel riquadro azioni. Quindi seleziona gli articoli disponibili e imposta il prezzo corrente. Un chiaro vantaggio dell'utilizzo del modello di inventario dei costi standard è che fa sì che il sistema rivaluta automaticamente l'inventario disponibile.
