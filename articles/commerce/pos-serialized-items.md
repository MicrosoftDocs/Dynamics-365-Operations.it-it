---
title: Utilizzare articoli serializzati nel POS
description: Questo argomento spiega come gestire gli articoli serializzati nell'applicazione POS (Point of Sale).
author: boycezhu
manager: annbe
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 0431ffa45eceac5c12d8ed991b00730c50ca62f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972557"
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

## <a name="sell-serialized-items-in-pos"></a>Vendere gli articoli serializzati in POS

Sebbene l'applicazione POS abbia sempre supportato la vendita di articoli serializzati, nella versione Commerce 10.0.17 e successive, le organizzazioni possono abilitare funzionalità che migliorano la logica di business che viene attivata quando si vendono prodotti configurati per la tracciabilità del numero di serie.

Quando la funzionalità **Convalida avanzata del numero di serie per acquisizione ordini POS ed evasione ordini** è abilitata, le seguenti configurazioni di prodotto vengono valutate quando si vendono prodotti serializzati in POS:

- **Tipo numero di serie** impostazione per il prodotto (**attivo** o **attivo in vendite**).
- **Emissione in bianco consentita** impostazioni per il prodotto.
- **Inventario fisico negativo** impostazioni per il prodotto e/o il magazzino di vendita.

### <a name="active-serial-configurations"></a>Configurazioni dei numeri di serie attivi

Quando gli articoli vengono venduti in POS configurati con una dimensione di tracciabilità del numero di serie **Attiva**, il POS avvia la logica di convalida che impedisce agli utenti di completare la vendita di un articolo serializzato con un numero di serie che non viene trovato nell'inventario corrente del magazzino di vendita. Esistono due eccezioni a questa regola di convalida:

- Se l'elemento è configurato anche con l'opzione **Emissione in bianco consentita** abilitata, gli utenti possono ignorare l'immissione del numero di serie e vendere l'articolo senza designazione del numero di serie.
- Se l'articolo e/o il magazzino di vendita è configurato con **Inventario fisico negativo** abilitato, l'applicazione accetta e vende un numero di serie di cui non è possibile confermare la presenza nell'inventario del magazzino da cui viene venduto. Questa configurazione consente alla transazione di magazzino per quello specifico articolo/numero di serie di diventare negativa e quindi il sistema consentirà la vendita di numeri di serie sconosciuti.

> [!IMPORTANT]
> Per garantire che l'applicazione POS possa convalidare correttamente se i numeri di serie venduti per gli articoli di tipo di numero di serie **Attivo** sono nell'inventario del magazzino di vendita, è necessario che le organizzazioni eseguano il processo **Disponibilità prodotto con dimensioni di tracciabilità** in Commerce headquarters e il processo di distribuzione della disponibilità del prodotto di accompagnamento **1130** in Commerce headquarters su base frequente. Quando il nuovo inventario serializzato viene ricevuto nei magazzini di vendita, affinché il POS possa convalidare la disponibilità dell'inventario dei numeri di serie venduti, la rappresentazione generale dell'inventario deve aggiornare frequentemente il database del canale con i dati sulla disponibilità dell'inventario più aggiornati. Il processo **Disponibilità prodotto con dimensioni di tracciabilità** acquisisce un'istantanea corrente dell'inventario principale, inclusi i numeri di serie, per tutti i magazzini dell'azienda. Il processo di distribuzione **1130** prende l'istantanea dell'inventario e la condivide con tutti i database di canale configurati.

### <a name="active-in-sales-process-serial-configurations"></a>Attivare le configurazioni dei numeri di serie nelle vendite

Gli articoli configurati con dimensione di numero di serie **Attiva in processo di vendita** non passano attraverso alcuna logica di convalida dell'inventario, poiché questa configurazione implica che i numeri di serie dell'inventario non sono preregistrati in magazzino e i numeri di serie vengono acquisiti solo al momento della vendita.  

Se **Emissione in bianco consentita** è configurato anche per gli articoli con l'opzione **Attiva in processo di vendita** configurata, l'immissione del numero di serie può essere ignorata. Se **Emissione in bianco consentita** non è configurato, l'applicazione richiede all'utente di inserire un numero di serie, anche se non verrà convalidato rispetto all'inventario disponibile.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Applicare i numeri di serie durante la creazione delle transazioni POS

L'applicazione POS richiede immediatamente agli utenti l'acquisizione del numero di serie quando si vende un articolo serializzato, ma l'applicazione consente agli utenti di saltare l'immissione dei numeri di serie fino a un certo punto del processo di vendita. Quando l'utente inizia ad acquisire il pagamento, l'applicazione applica e richiede l'immissione del numero di serie per tutti gli articoli che non sono configurati per essere evasi tramite spedizioni o ritiri futuri. Tutti gli articoli con numero di serie configurati per il pagamento in contanti o l'evasione degli ordini richiedono che l'utente acquisisca il numero di serie (o accetti di lasciarlo vuoto se la configurazione dell'articolo lo consente) prima di completare la vendita.

Per gli articoli con numero di serie venduti per il ritiro o la spedizione futuri, gli utenti POS possono saltare l'inserimento iniziale del numero di serie e completare comunque la creazione dell'ordine del cliente.   

> [!NOTE]
> Quando si vendono o si evadono prodotti con numero di serie tramite l'applicazione POS, viene applicata una quantità di "1" per gli articoli con numero di serie nella transazione di vendita. Questo è il risultato del modo in cui le informazioni sul numero di serie vengono tracciate nella riga di vendita. Quando si vende o si evade una transazione per più articoli con numero di serie tramite POS, ogni riga di vendita deve essere configurata solo con una quantità di "1". 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Applicare i numeri di serie durante l'evasione o il ritiro dell'ordine cliente

Quando si evadono le righe ordine cliente per i prodotti con numero di serie utilizzando l'operazione **Evasione ordini** in POS, POS impone l'acquisizione del numero di serie prima dell'evasione finale. Pertanto, se un numero di serie non è stato fornito durante l'acquisizione dell'ordine iniziale, deve essere acquisito durante i processi di prelievo, imballaggio o spedizione nel POS. Ad ogni passaggio viene eseguita una convalida e all'utente verranno richiesti solo i dati del numero di serie se mancano o non sono più validi. Ad esempio, se un utente salta le fasi di prelievo o imballaggio e avvia immediatamente una spedizione e per la riga non è stato registrato un numero di serie, il POS richiederà l'inserimento del numero di serie prima del completamento della fase di fatturazione finale. Quando si impone l'acquisizione del numero di serie durante le operazioni di evasione degli ordini in POS, tutte le regole menzionate in precedenza in questo argomento vengono comunque applicate. Solo gli articoli con numero di serie configurati come **Attivo** passano attraverso una convalida dello stock di inventario del numero di serie. Gli articoli configurati come **Attivo nel processo di vendita** non verranno convalidati. Se **Inventario fisico negativo** è consentito i prodotti **attivi**, sarà accettato qualsiasi numero di serie, indipendentemente dalla disponibilità di magazzino. Per gli articoli **attivi** e **attivi nel processo di vendita**, se **Emissione in bianco consentita** è configurato, un utente può lasciare i numeri di serie vuoti se lo desidera durante le fasi di prelievo, imballaggio e spedizione.

Le convalide dei numeri di serie si verificheranno anche quando un utente esegue le operazioni di ritiro sugli ordini dei clienti nel POS. L'applicazione POS non consente di finalizzare un ritiro su un prodotto serializzato a meno che non superi le convalide come menzionato in precedenza. Le convalide sono sempre basate sulla dimensione di tracciabilità del prodotto e sulle configurazioni del magazzino di vendita. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Operazione di magazzino in ingresso in POS](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Operazione di magazzino in uscita in POS](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)
