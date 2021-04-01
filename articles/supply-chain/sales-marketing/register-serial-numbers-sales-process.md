---
title: Utilizzo degli articoli serializzati
description: In questo argomento viene descritto come registrare i numeri di serie sui documenti di trasporto o sulle fatture durante il processo di vendita. Si tratta di una funzionalità utile se una società desidera acquisire numeri di serie solo per scopi di garanzia e assistenza senza dover gestire i numeri di serie dall'entrata all'uscita delle merci in magazzino.
author: omulvad
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba21fd5c3dc425236b7b0ae91b355c522b937a6d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231842"
---
# <a name="working-with-serialized-items"></a>Utilizzo degli articoli serializzati

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come registrare i numeri di serie sui documenti di trasporto o sulle fatture durante il processo di vendita. Si tratta di una funzionalità utile se una società desidera acquisire numeri di serie solo per scopi di garanzia e assistenza senza dover gestire i numeri di serie dall'entrata all'uscita delle merci in magazzino.

Molte società desiderano acquisire numeri di serie solo per scopi di garanzia e assistenza per non dover gestire i numeri di serie dall'entrata all'uscita delle merci in magazzino. In questi scenari, è possibile registrare i numeri di serie sui documenti di trasporto o sulle fatture quando i prodotti vengono venduti. Se in seguito i prodotti vengono resi, è quindi possibile tenere traccia di ogni prodotto in una fattura per determinare se è stato venduto e se gli obblighi di assistenza e garanzia sono validi.

È necessario abilitare i numeri di serie per il processo di vendita selezionando l'opzione **Attiva in processo di vendita** nella pagina **Gruppi di dimensioni di tracciabilità**. Gli eventi seguenti si verificano in Supply Chain Management:
-   Nella scheda dettagli **Numeri di serie**, è selezionata l'opzione **Controllo numero di serie**. Se questa opzione è selezionata, è necessario registrare un numero di serie per ogni articolo sul documento di trasporto o sulla fattura.
-   Tutte le selezioni nel gruppo di dimensioni di tracciabilità per i numeri di serie vengono deselezionate, tranne la casella di controllo **Uscita non specificata consentita**. È possibile selezionare la casella di controllo **Uscita non specificata consentita** per eseguire l'override del controllo del numero di serie e consentire l'imballaggio e la fatturazione dei prodotti senza registrare i numeri di serie.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>Quando si possono registrare i numeri di serie nel processo di vendita?
È possibile registrare i numeri di serie sul documento di trasporto per un ordine cliente o sulla fattura. Quando si prepara una fattura per un articolo serializzato fornito con un documento di trasporto, è possibile selezionare i numeri di serie sul documento di trasporto da fatturare. La quantità di numeri di serie registrati non deve superare quella degli articoli spediti. Se si crea una fattura parziale, è possibile selezionare meno articoli serializzati rispetto a quelli registrati sul documento di trasporto. Quando si stampa un documento di trasporto o una fattura, i numeri di serie registrati vengono inclusi.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>È possibile immettere i numeri di serie digitalizzandoli o è necessario digitarli?
È possibile digitalizzare o immettere i numeri di serie. Quando si utilizza uno scanner, la modalità di scansione determina se aggiungere o rimuovere i numeri di serie dall'elenco di numeri di serie sulla fattura o sul documento di trasporto. Se si desidera digitalizzare i numeri di serie, ad esempio utilizzando un lettore di codice a barre portatile, configurare lo scanner per inviare un comando Immetti o di tabulazione dopo il numero di serie. In questo modo verrà indicata la fine del flusso di dati. In caso contrario, è necessario premere INVIO o TAB sulla tastiera dopo aver digitalizzato ogni numero di serie.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Se si abilitano i numeri di serie per il processo di vendita, è necessario registrare tutti i numeri di serie per tutti gli articoli?
L'impostazione del gruppo di dimensioni di tracciabilità assegnato al prodotto determina se i numeri di serie devono essere registrati per tutti gli articoli su un documento di trasporto o su una fattura. Quando si abilitano i numeri di serie per il processo di vendita, la casella di controllo, l'opzione **Controllo numero di serie** viene selezionata automaticamente. Pertanto, è necessario registrare un numero di serie o una registrazione vuota per un numero illeggibile, per ogni articolo sul documento di trasporto o sulla fattura. Se non si desidera richiedere un numero di serie per ogni articolo, selezionare la casella di controllo **Uscita non specificata consentita** nel gruppo di dimensioni di tracciabilità assegnato all'articolo. È quindi possibile registrare meno numeri di serie rispetto alla quantità di articoli spediti. Se si registrano più numeri di serie della quantità di articoli spediti, non sarà possibile registrare il documento di trasporto o la fattura.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>È possibile registrare i numeri di serie per le fatture parziali e le spedizioni parziali?
È possibile creare fatture e documenti di trasporto parziali per gli ordini cliente e registrare i numeri di serie solo per gli articoli inclusi. Se si desidera creare una fattura parziale e si dispone di più documenti di trasporto per l'ordine cliente, è possibile includere i numeri di serie da più documenti di trasporto. Tuttavia, può esistere un solo documento di trasporto in cui non sono inclusi tutti i numeri di serie. Ad esempio, se si dispone di tre documenti di trasporto e ognuno include due articoli serializzati, non è possibile creare una fattura parziale per un articolo da ciascun documento di trasporto.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>Quali operazioni si possono eseguire se un numero di serie non è leggibile?
Se un numero di serie non può essere letto o digitalizzato, è possibile creare una riga vuota per l'articolo facendo clic su **Non leggibile** nella pagina **Numeri di serie**. Se il numero di serie diventa disponibile in seguito, è possibile aggiornare la fattura o il documento di trasporto. Per ulteriori informazioni, vedere la sezione successiva ""È possibile correggere o modificare i numeri di serie registrati per un ordine cliente?"

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>È possibile correggere o modificare i numeri di serie registrati per un ordine cliente?
Sì, e possibile correggere i numeri di serie se vengono soddisfatte le seguenti condizioni:
-   **Fatture**: è possibile modificare i numeri di serie per gli articoli non ancora fatturati. Anche il documento di trasporto viene aggiornato. Tuttavia, se una riga ordine cliente è stata corretta registrando una quantità negativa, non è possibile modificare i numeri di serie di questa riga.
-   **Documenti di trasporto**: non è possibile correggere parzialmente una riga del documento di trasporto contenente gli articoli serializzati. È necessario stornare la quantità totale della riga. Se un documento di trasporto è stato annullato o corretto, non è necessario registrare di nuovo i numeri di serie stornati quando si crea un nuovo documento di trasporto per gli stessi articoli serializzati. Verranno utilizzati i numeri registrati.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>È possibile visualizzare i numeri di serie forniti con un documento di trasporto specifico o inclusi in una fattura?
Sì, è possibile eseguire una richiesta di informazioni nella riga del giornale di registrazione del documento di trasporto o nella riga del giornale di registrazione fatture per visualizzare un elenco di tutti i numeri di serie inclusi nel documento.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>È possibile visualizzare gli articoli serializzati di cui si dispone?
No, non è possibile visualizzare gli articoli serializzati di cui si dispone poiché i numeri di serie degli articoli non vengono registrati finché i prodotti non vengono venduti.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>È possibile registrare i numeri di serie per gli articoli a peso variabile?
No, durante il processo di vendita non è possibile registrare i numeri di serie per gli articoli a peso variabile. Inoltre, se il prodotto è impostato come articolo a peso variabile, non è possibile assegnare il prodotto a un gruppo di dimensioni di tracciabilità impostato per l'utilizzo dei numeri di serie solo durante il processo di vendita.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>Posso registrare i numeri di serie presso i terminali Retail POS?

Sì, al terminale Retail POS verrà richiesto all'utente di immettere un numero di serie quando l'utente vende un articolo assegnato a un gruppo di dimensioni di tracciabilità impostato per l'utilizzo dei numeri di serie solo durante il processo di vendita.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Quali ruoli di sicurezza sono necessari per registrare i numeri di serie durante il processo di vendita?
Questa funzionalità è disponibile per tutti i ruoli che possono gestire i documenti di trasporto e le fatture di vendita. I compiti seguenti consentono ai lavoratori di correggere i numeri di serie e registrare voci vuote per i numeri di serie che non possono essere letti o sottoposti a scansione:
-   Gestisci correzioni dei numeri di serie
-   Gestisci registrazione dei numeri di serie non leggibili







[!INCLUDE[footer-include](../../includes/footer-banner.md)]