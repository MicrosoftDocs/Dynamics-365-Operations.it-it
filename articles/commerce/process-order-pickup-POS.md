---
title: Elaborare i ritiri degli ordini dei clienti in POS
description: In questo articolo viene illustrata la funzionalità disponibile nell'applicazione POS per l'elaborazione dei ritiri degli ordini dei clienti.
author: Hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0a886f156fff96f3b7e6026c405d3c8700d57f62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910471"
---
# <a name="process-customer-order-pickups-in-pos"></a>Elaborare i ritiri degli ordini dei clienti in POS

[!include [banner](includes/banner.md)]

Quando un [ordine del cliente](customer-orders-overview.md) viene creato per il ritiro in negozio, un utente del negozio può utilizzare l'applicazione punto vendita (POS) per avviare il ritiro dell'articolo. Il POS eseguirà l'acquisizione del pagamento finale come richiesto. Completerà inoltre l'inventario e la registrazione finanziaria per le quantità prelevate.

Se sei un utente del negozio, puoi eseguire il ritiro utilizzando l'operazione **Richiama ordine** o l'operazione **Evasione ordini** in POS. Per rendere disponibile l'operazione **Preleva** è necessario prima seguire uno di questi passaggi:

- Per utilizzare l'operazione **Richiama ordine** cerca e seleziona l'ordine che verrà ritirato.
- Per utilizzare l'operazione **Evasione ordini** cerca e seleziona una o più righe d'ordine.

Se l'ordine o le righe d'ordine selezionati non sono configurati per il ritiro in quel negozio specifico, o se l'ordine è già stato completamente ritirato, l'operazione **Preleva** non sarà disponibile.

![Operazione preleva.](media/pickupoperation.png)

In Microsoft Dynamics 365 Commerce versione 10.0.17 e successive, la funzionalità **Esperienza utente migliorata per l'elaborazione degli ordini di ritiro nel punto vendita** può essere attivata tramite la gestione delle funzionalità in Commerce headquarters. Se questa funzione è disattivata, gli utenti non possono selezionare le quantità di prelievo. Per impostazione predefinita, la quantità completa ordinata per la riga è la quantità che verrà prelevata. Questa esperienza può essere problematica, perché gli utenti potrebbero dimenticare di selezionare alcuni articoli per il ritiro quando effettuano il ritiro tramite l'evasione dell'ordine.

La funzionalità **Esperienza utente migliorata per l'elaborazione degli ordini di ritiro nel punto vendita** offre agli utenti un maggiore controllo sulla selezione dei prodotti che verranno prelevati e sulla quantità di tali prodotti che verranno ritirati. Gli utenti non devono selezionare ogni riga dell'ordine di vendita nella pagina di evasione dell'ordine prima di selezionare **Preleva**. Verranno visualizzati tutti gli articoli che possono essere ritirati. Gli utenti possono specificare più righe per il ritiro anche se è selezionata una sola riga di prodotto.

Quando la funzionalità **Esperienza utente migliorata per l'elaborazione degli ordini di ritiro nel punto vendita** è attivata e selezioni l'operazione **Preleva**, la finestra di dialogo **Preleva** viene visualizzata. Qui puoi selezionare gli articoli e le quantità che verranno prelevate. Per impostazione predefinita, qualsiasi quantità ordinata con inventario in uno stato prelevato o imballato è considerata idonea per il ritiro. Per impostazione predefinita, tale quantità è impostata come quantità di prelievo. È possibile modificare la quantità immessa, a condizione che la quantità non sia 0 (zero) e non superi la quantità totale aperta (ovvero non fatturata) per la riga selezionata.

![Finestra di dialogo Preleva.](media/pickupselect.png)

Dopo aver selezionato le quantità che verranno prelevate e quindi selezionato **Preleva**, viene visualizzata la pagina della transazione. Se la funzionalità [pagamenti multicanale](omni-channel-payments.md) è attivata e sono presenti pagamenti con carta di credito pre-autorizzati in archivio, è necessario applicare il pagamento.

Nella pagina della transazione, il sistema calcola gli importi dovuti calcolando il totale dovuto per gli articoli di ritiro selezionati e quindi sottraendo eventuali depositi precedentemente applicati o pagamenti con carta di credito autorizzati. È necessario elaborare il pagamento per completare la transazione di ritiro. Se il [layout dello schermo](pos-screen-layouts.md) della pagina della transazione è configurato in modo da includere l'operazione **Concludi transazione** e nessun importo è dovuto, è possibile completare la transazione senza selezionare un metodo di pagamento. Se l'operazione **Concludi transazione** non è disponibile, è possibile selezionare il collegamento **Importo di $ 0,00 dovuto** nel riquadro **Totali** per concludere la transazione senza dover selezionare un metodo di pagamento.

![Pagina Transazione per una transazione di ritiro dell'ordine cliente.](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Modifica delle righe o delle quantità di prelievo

Se è necessario modificare la quantità di prelievo dopo aver selezionato gli articoli che verranno ritirati, è possibile selezionare **Imposta quantità**. Non è possibile impostare la quantità di ritiro su **0** (zero) o aumentarla a un valore che supera la quantità non fatturata che rimane per la riga ordinata. Per rimuovere una riga di ritiro dal carrello delle transazioni, seleziona **Annulla transazione**. La transazione corrente verrà interrotta e il flusso per l'operazione **Preleva** verrà riavviata.

Se la funzionalità **Esperienza utente migliorata per l'elaborazione degli ordini di ritiro nel punto vendita** è attivata, le organizzazioni possono aggiungere un pulsante per l'opzione **Cambia righe di ritiro** al layout dello schermo della pagina della transazione. Dopo aver creato il carrello delle transazioni di ritiro in POS e aver selezionato gli articoli, è possibile selezionare **Cambia righe di ritiro** se devi cambiare gli articoli da ritirare ma non vuoi annullare l'intera transazione. Nella finestra di dialogo **Cambia righe di ritiro** visualizzata, puoi modificare gli articoli e le quantità di prelievo. Il carrello delle transazioni viene quindi aggiornato per riflettere le modifiche.

![Finestra di dialogo Cambia articoli di prelievo.](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]