---
title: Utilizzare articoli serializzati nel POS
description: Questo argomento spiega come gestire gli articoli serializzati nell'applicazione POS (Point of Sale).
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978365"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Utilizzare articoli serializzati nel POS

[!include [banner](includes/banner.md)]

Molti rivenditori vendono prodotti che richiedono il controllo seriale. Questi prodotti sono indicati come *articoli serializzati*. È possibile che alcuni rivenditori desiderino voler mantenere i numeri di serie nelle scorte magazzino o punto vendita ai fini della tracciabilità. Altri rivenditori potrebbero voler acquisire i numeri di serie durante il processo di vendita, ai fini dell'assistenza e della garanzia. Questo argomento spiega come gestire gli articoli serializzati nell'applicazione POS (Point of Sale) Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurazioni dei numeri di serie

Un articolo viene considerato serializzato se dispone dell'assegnazione di un gruppo di dimensioni di tracciabilità impostato per consentire i numeri di serie. In Commerce headquarters, nella pagina **Gruppi di dimensioni di tracciabilità**, selezionare l'opzione **Attiva** per abilitare i numeri di serie per il processo di inventario o selezionare l'opzione **Attiva nel processo di vendita** per abilitare i numeri di serie per il processo di vendita.

Nella Scheda dettaglio **Dimensioni di tracciabilità**, attivare il parametro **Entrata non specificata consentita** per consentire al numero di serie di essere un input opzionale durante il processo di entrata in magazzino dell'articolo serializzato. La disattivazione di questo parametro impone che il numero di serie sia un input obbligatorio. Allo stesso modo, il parametro **Uscita non specificata consentita** controlla se il numero di serie è richiesto durante il processo di spedizione delle scorte.

> [!NOTE]
> Per utilizzare le operazioni POS **Magazzino in entrata** e **Magazzino in uscita** per registrare o convalidare i numeri di serie per un articolo serializzato, è necessario configurare che all'articolo venga assegnato un gruppo di dimensioni di tracciabilità impostato per consentire l'uso di numeri seriali per l'opzione **Attiva**, anziché l'opzione **Attiva in processo di vendita**.

## <a name="serial-number-management-page"></a>Pagina Gestione numeri di serie

Nelle operazioni POS **Inventario in entrata** e **Inventario in uscita**, se l'articolo che viene selezionato, ricevuto o spedito è un articolo serializzato, il riquadro **Dettagli** contiene l'opzione **Gestisci numero di serie** che apre la pagina **Gestione numeri di serie** in cui è possibile registrare o convalidare i numeri di serie dell'articolo. In alternativa, è possibile aprire la pagina **Gestione numeri di serie** selezionando l'azione **Numero di serie** nella barra dell'app della visualizzazione dei dettagli dell'ordine o selezionando l'opzione **Gestisci numero di serie** nella finestra di dialogo di richiesta visualizzata durante il processo di ricezione o spedizione. 

La pagina **Gestione numeri di serie** elenca tutte le righe di numeri di serie aperte in attesa di registrazione o convalida. In questa pagina potrebbero essere presenti due schede: una per l'articolo corrente e un'altra per tutti gli articoli serializzati nell'ordine.

Il campo **Stato** nella pagina **Gestione numeri di serie** fornisce informazioni sulla fase corrente in cui si trova ciascun numero di serie:

- **Non registrato**: il numero di serie non è stato specificato oppure il numero di serie preregistrato non è ancora stato convalidato (nel processo di ricezione).
- **In registrazione**: il numero di serie è stato registrato e salvato in locale nel database del canale del negozio oppure il numero di serie preregistrato è stato convalidato. Solo i numeri di serie con stato **In registrazione** verranno inviati a Commerce headquarters al termine della ricezione o dell'evasione.

## <a name="receive-serialized-items"></a>Ricevimento di articoli serializzati

L'operazione POS **Magazzino in entrata** consente agli utenti di eseguire queste attività per gli articoli serializzati:

- Registrare i numeri di serie per gli articoli serializzati quando tali articoli vengono ricevuti nel negozio tramite un ordine fornitore.
- Convalidare i numeri di serie preregistrati per gli articoli serializzati quando tali articoli vengono ricevuti nel negozio tramite un ordine fornitore o un ordine di trasferimento.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrare i numeri di serie per gli articoli serializzati

Per un ordine fornitore, viene visualizzata una finestra di dialogo con l'opzione **Gestisci numero di serie** durante il processo di ricezione di un articolo serializzato. È possibile selezionare tale opzione per aprire la pagina **Gestione numeri di serie** e iniziare a registrare i numeri di serie. È inoltre possibile ignorare questo passaggio durante il processo di ricezione e fornire l'input in un secondo momento, prima che l'entrata venga registrata.

Per impostazione predefinita, viene visualizzata la scheda per l'articolo corrente. Tutte le righe di numeri di serie hanno un valore di numero di serie vuoto e uno stato **Non registrato**. È possibile eseguire la scansione dei codici a barre dei numeri di serie oppure selezionare **Numero di serie** sulla barra dell'app per inserire continuamente i numeri di serie. I numeri di serie immessi vengono visualizzati nell'elenco e lo stato viene modificato su **In registrazione**. Il numero massimo di numeri di serie che è possibile registrare nell'elenco è uguale alla quantità ricevuta. Se si commette un errore, è possibile selezionare **Modifica** o **Cancella** nel riquadro **Dettagli** per apportare modifiche ai numeri di serie inseriti.

È inoltre possibile registrare i numeri di serie nella scheda **Tutti gli articoli serializzati** della pagina **Gestione numeri di serie**. Nell'elenco selezionare l'articolo per il quale si desidera registrare i numeri di serie.

### <a name="validate-serial-numbers-on-serialized-items"></a>Convalidare i numeri di serie su articoli serializzati

Per un ordine di trasferimento, il lato in uscita deve preregistrare i numeri di serie sugli articoli serializzati durante il processo di spedizione. Per un ordine di fornitore, il fornitore può fornire le informazioni sul numero di serie tramite un Advance Shipment Notice (ASN) ed è possibile preregistrare i numeri sugli articoli che verranno spediti. In entrambi i casi, i numeri di serie sono noti prima della ricezione. Sul lato in entrata è pertanto necessario confermare solo di aver ricevuto gli articoli previsti.

Per convalidare i numeri di serie, è possibile aprire la pagina **Gestione numeri di serie** durante il processo di ricezione o in qualsiasi momento prima della registrazione della ricevuta. Per ogni articolo serializzato con numeri di serie preregistrati, tutti i numeri di serie vengono automaticamente impostati sullo stato iniziale **Non registrato** su questa pagina. Per convalidare i numeri di serie, è possibile eseguirne la scansione o inserirli. Quando un numero di serie viene inserito, l'applicazione verifica se corrisponde ai numeri di serie preregistrati. In caso di corrispondenza, il relativo stato viene modificato in **In registrazione**. In caso contrario, viene visualizzato un messaggio di errore. In alternativa, è possibile selezionare direttamente un numero di serie, quindi selezionare l'opzione **Convalida numero di serie** nel riquadro **Dettagli** per contrassegnare rapidamente il numero di serie come convalidato. Il numero massimo di numeri di serie che è possibile convalidare nell'elenco è uguale alla quantità ricevuta.

È inoltre possibile convalidare i numeri di serie nella scheda **Tutti gli articoli serializzati** della pagina **Gestione numeri di serie**. Nell'elenco selezionare l'articolo per il quale si desidera convalidare i numeri di serie.

## <a name="ship-serialized-items"></a>Spedire articoli serializzati

È possibile usare l'opzione **Magazzino in uscita** per registrare i numeri di serie rispetto agli articoli serializzati quando vengono spediti fuori dal negozio corrente tramite un ordine di trasferimento.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrare i numeri di serie per gli articoli serializzati

Per un ordine di trasferimento, viene visualizzata una finestra di dialogo con l'opzione **Gestisci numero di serie** durante il processo di spedizione di un articolo serializzato. È possibile selezionare l'opzione per aprire la pagina **Gestione numeri di serie** e iniziare a registrare i numeri di serie. È inoltre possibile ignorare questo passaggio durante il processo di spedizione e fornire l'input in un secondo momento, prima che la spedizione venga registrata.

Per impostazione predefinita, viene visualizzata la scheda per l'articolo corrente. Tutte le righe di numeri di serie hanno un valore di numero di serie vuoto e uno stato **Non registrato**. È possibile eseguire la scansione dei codici a barre dei numeri di serie oppure selezionare **Numero di serie** sulla barra dell'app per inserire continuamente i numeri di serie. I numeri di serie immessi vengono visualizzati nell'elenco e lo stato viene modificato su **In registrazione**. Il numero massimo di numeri di serie che è possibile registrare nell'elenco è uguale alla quantità spedita. Se si commette un errore, è possibile selezionare **Modifica** o **Cancella** nel riquadro **Dettagli** per apportare modifiche ai numeri di serie inseriti.

È inoltre possibile registrare i numeri di serie nella scheda **Tutti gli articoli serializzati** nella pagina **Gestione numeri di serie**. Nell'elenco selezionare l'articolo per il quale si desidera registrare i numeri di serie.

Facoltativamente, è possibile abilitare la convalida della disponibilità del numero di serie durante la registrazione del numero di serie rispetto a un ordine di trasferimento in uscita. Con questa convalida, se si tenta di spedire un numero di serie che non è disponibile nell'inventario del negozio di spedizione, verrà visualizzato un messaggio di errore e sarà necessario fornire un numero diverso.

Per abilitare tale convalida, come prerequisito, è necessario pianificare i seguenti processi in modo che vengano eseguiti su base ricorrente:

- **Retail e Commerce** > **Vendita al dettaglio e commercio IT** > **Prodotti e inventario** > **Disponibilità prodotto con dimensioni di tracciabilità**
- **Retail e Commerce** > **Programmazioni della distribuzione** > **1130** (**Disponibilità del prodotto**)

## <a name="additional-resources"></a>Risorse aggiuntive

[Operazione di magazzino in ingresso in POS](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Operazione di magazzino in uscita in POS](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
