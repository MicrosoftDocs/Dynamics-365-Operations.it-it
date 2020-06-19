---
title: Utilizzare articoli serializzati nel POS
description: Questo argomento spiega come gestire gli articoli serializzati nell'applicazione POS (Point of Sale).
author: boycezhu
manager: annbe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: eedb64ae04345cb94bdd8cc68de833cfcfd40119
ms.sourcegitcommit: 39981582778b0a62567324452485a6721ca18284
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "3407500"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Utilizzare articoli serializzati nel POS

[!include [banner](includes/banner.md)]

Molti rivenditori vendono prodotti che richiedono il controllo seriale. Questi articoli sono indicati come *articoli serializzati*. È possibile che alcuni rivenditori desiderino voler mantenere i numeri di serie ai fini della tracciabilità. Altri rivenditori potrebbero voler acquisire i numeri di serie durante il processo di vendita, ai fini dell'assistenza e della garanzia. Questo argomento spiega come gestire gli articoli serializzati nell'applicazione POS (Point of Sale) Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurazioni dei numeri di serie

Un articolo viene considerato serializzato se dispone dell'assegnazione di un gruppo di dimensioni di tracciabilità impostato per consentire i numeri di serie. In Commerce headquarters selezionare l'opzione **Attiva** nella pagina **Gruppi di dimensioni di tracciabilità** per abilitare i numeri di serie per il processo di inventario. Per abilitare i numeri di serie per il processo di vendita, selezionare l'opzione **Attiva in processo di vendita**.

Nella Scheda dettaglio **Dimensioni di tracciabilità**, se l'opzione **Entrata non specificata consentita** è attivata, il numero di serie è un input opzionale durante il processo di entrata in magazzino. Se l'opzione è disattivata, è richiesto il numero di serie.

Nella Scheda dettaglio **Numeri di serie**, se l'opzione **Controllo numero di serie** è attivata, il numero di serie deve essere univoco per unità. In altre parole, i numeri di serie duplicati non sono ammessi.

## <a name="serialized-items-in-the-receiving-process"></a>Articoli serializzati nel processo di ricezione

L'operazione **Magazzino in entrata** nell'applicazione POS consente agli utenti di eseguire queste attività per gli articoli serializzati:

- Registrare i numeri di serie per gli articoli serializzati quando tali articoli vengono ricevuti nel negozio tramite un ordine fornitore.
- Convalidare i numeri di serie preregistrati per gli articoli serializzati quando tali articoli vengono ricevuti nel negozio tramite un ordine fornitore o un ordine di trasferimento.

> [!NOTE]
> Per utilizzare l'operazione **magazzino in entrata** per registrare o convalidare un articolo serializzato, è necessario che all'articolo sia assegnato un gruppo di dimensioni di tracciabilità impostato per consentire l'uso di numeri seriali per l'opzione **Attiva**, anziché l'opzione **Attiva in processo di vendita**.

Per iniziare il processo di ricezione, nell'operazione **Magazzino in entrata** è possibile iniziare nella visualizzazione **In ricevimento ora**, eseguendo la scansione del codice a barre dell'articolo o inserendo l'ID articolo. In alternativa, è possibile iniziare nella visualizzazione **Elenco completo ordini**, selezionando manualmente l'articolo.

Se l'articolo che viene selezionato o ricevuto è un articolo serializzato, il riquadro **Dettagli** per l'articolo contiene un collegamento **Gestisci numero di serie** che apre la pagina **Gestione numeri di serie**. In alternativa, è possibile aprire la pagina **Gestione numeri di serie** selezionando **Numero di serie** nella barra dell'app della visualizzazione dei dettagli dell'ordine o selezionando **Gestisci numero di serie** nella finestra di dialogo di richiesta visualizzata durante il processo di ricezione. La pagina **Gestione numeri di serie** elenca tutte le righe di numeri di serie aperte in attesa di registrazione o convalida. In questa pagina potrebbero essere presenti due schede: una per l'articolo corrente e una per tutti gli articoli serializzati nell'ordine.

Il campo **Stato** nella pagina **Gestione numeri di serie** fornisce informazioni sulla fase corrente in cui si trova ciascun numero di serie:

- **Non registrato**: il numero di serie non è stato specificato oppure il numero di serie preregistrato non è ancora stato convalidato.
- **In registrazione**: il numero di serie è stato registrato e salvato in locale nel database del canale del negozio oppure il numero di serie preregistrato è stato convalidato. Solo i numeri di serie con stato **In registrazione** verranno inviati a Commerce headquarters al termine della ricezione.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrare i numeri di serie per gli articoli serializzati

Per un ordine fornitore, in una finestra di dialogo di richiesta visualizzata durante il processo di ricezione viene resa disponibile l'opzione **Gestisci numero di serie**. È possibile selezionare tale opzione per aprire la pagina **Gestione numeri di serie** e iniziare a registrare i numeri di serie. È inoltre possibile ignorare questo passaggio durante il processo di ricezione e fornire l'input in un secondo momento, prima che l'entrata venga registrata.

Per impostazione predefinita, viene visualizzata la scheda per l'articolo corrente. Tutte le righe di numeri di serie hanno un valore di numero di serie vuoto e uno stato **Non registrato**. È possibile eseguire la scansione dei codici a barre dei numeri di serie oppure selezionare **Numero di serie** sulla barra dell'app per inserire continuamente i numeri di serie nella finestra di dialogo. I numeri di serie immessi vengono visualizzati nell'elenco e lo stato delle righe dei numeri di serie viene modificato in **In registrazione**. Il numero massimo di numeri di serie che è possibile registrare nell'elenco è uguale alla quantità ricevuta. Se si commette un errore, è possibile selezionare **Modifica** o **Cancella** nel riquadro **Dettagli** per apportare modifiche ai numeri di serie inseriti.

È inoltre possibile registrare i numeri di serie nella scheda **Tutti gli articoli serializzati** della pagina **Gestione numeri di serie**. Nell'elenco selezionare l'articolo per il quale si desidera registrare i numeri di serie.

Durante la registrazione dei numeri di serie su questa pagina, viene eseguita la convalida della duplicazione. Se si tenta di immettere un numero di serie duplicato per un articolo per il quale è attivato il controllo del numero di serie, viene visualizzato un messaggio di errore ed è necessario specificare un numero diverso.

### <a name="validate-serial-numbers-on-serialized-items"></a>Convalidare i numeri di serie su articoli serializzati

Per un ordine di trasferimento, il lato in uscita deve preregistrare i numeri di serie sugli articoli serializzati durante il processo di spedizione. Per un ordine di fornitore, il fornitore può fornire le informazioni sul numero di serie tramite un Advance Shipment Notice (ASN) ed è possibile preregistrare i numeri sugli articoli che verranno spediti. In entrambi i casi, i numeri di serie sono noti prima della ricezione. Sul lato in entrata è pertanto necessario confermare solo di aver ricevuto gli articoli previsti.

Per convalidare i numeri di serie, è possibile aprire la pagina **Gestione numeri di serie** durante il processo di ricezione o in qualsiasi momento prima della registrazione della ricevuta. Per ogni articolo serializzato con numeri di serie preregistrati, tutti i numeri di serie vengono automaticamente impostati sullo stato iniziale **Non registrato** su questa pagina. Per convalidare i numeri di serie, è possibile eseguirne la scansione o inserirli. Quando un numero di serie viene inserito, l'applicazione verifica se corrisponde ai numeri di serie preregistrati. In caso di corrispondenza, il relativo stato viene modificato in **In registrazione**. In caso contrario, viene visualizzato un messaggio di errore. Il numero massimo di numeri di serie che è possibile convalidare nell'elenco è uguale alla quantità ricevuta.

È inoltre possibile convalidare i numeri di serie nella scheda **Tutti gli articoli serializzati** della pagina **Gestione numeri di serie**. Nell'elenco selezionare l'articolo per il quale si desidera convalidare i numeri di serie.

## <a name="additional-resources"></a>Risorse aggiuntive

[Operazione di magazzino in ingresso in POS](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
