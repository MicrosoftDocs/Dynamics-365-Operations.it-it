---
title: Impostare conti fornitore
description: "In questo argomento vengono descritti i tipi di informazioni che è necessario specificare quando si crea un nuovo conto fornitore."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2f0ddf0e4cff0d799a7baf6bdc9d5c2da0622f4d
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="set-up-vendor-accounts"></a>Impostare conti fornitore

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritti i tipi di informazioni che è necessario specificare quando si crea un nuovo conto fornitore.

Quando si crea un conto fornitore, è necessario immettere le informazioni sul fornitore. Queste informazioni vengono utilizzate per immettere automaticamente i dati nei documenti e seguire l'attività che coinvolge il fornitore. Ad esempio, è possibile configurare le seguenti informazioni per un fornitore:

-   Assegnare un gruppo di fornitori. È necessario assegnare ogni fornitore a un gruppo di fornitori. I fornitori inclusi in un gruppo condividono parametri. Possono avere ad esempio gli stessi termini di pagamento.
-   Configurare il fornitore per l'importazione del catalogo. I fornitori possono fornire un file contenente il catalogo degli articoli e servizi forniti. Questo file può essere caricato in modo che i lavoratori possano ordinare dal fornitore.
-   Consente di assegnare il fornitore alle categorie di approvvigionamento.
-   Consentire a un fornitore esistente di svolgere attività commerciali con un'altra persona giuridica nell'organizzazione.
-   Mettere in sospeso un fornitore per determinati tipi di transazioni.
-   Impostare le coordinate bancarie per il fornitore in modo da poter inviare pagamenti elettronicamente.
-   Impostare le informazioni su IVA, consegna, fattura e pagamento per il fornitore. Per impostazione predefinita, queste impostazioni vengono copiate nei nuovi documenti creati per il fornitore.
-   Impostare le dimensioni finanziarie predefinite che vengono utilizzate per registrare automaticamente le transazioni con il fornitore nei conti finanziari.

Per accelerare il processo di creazione conti fornitore, è possibile creare modelli. Per creare un modello, nel riquadro azioni della pagina **Fornitore** fare clic su **Opzioni** &gt; **Informazioni sui record**. Fare clic su **Modello di account società**. I modelli di account società sono condivisi con altri utenti.  

È inoltre possibile creare un modello utente per proprio uso. Non è possibile eliminare un fornitore se questo è associato ad altri record, ad esempio contatti o prodotti.

## <a name="vendor-account-numbers"></a>Numeri conto fornitore
Il numero di conto è un identificatore univoco per un fornitore. È possibile impostare numeri di conto in modo che vengano generati automaticamente al momento della creazione di un fornitore. È inoltre possibile configurare la sequenza numerica in modo da inserire manualmente i numeri di conto. Ad esempio, potrebbe essere utile utilizzare il numero di telefono del fornitore come identificatore.

## <a name="vendor-organizations-and-individual-vendors"></a>Organizzazioni fornitore e singoli fornitori
Quando si crea un nuovo conto fornitore, sarà necessario selezionare se il fornitore è un'organizzazione o una persona. L'opzione selezionata determina le informazioni che è necessario inserire per il fornitore. Per una persona, queste informazioni includono il nome, il cognome e il titolo. Per un'organizzazione, queste informazioni includono il numero di organizzazione e il numero di dipendenti.

## <a name="addresses"></a>Indirizzi
Per ciascun fornitore, è possibile definire più indirizzi, ciascuno dei quali viene utilizzato per uno scopo diverso. Ad esempio, è possibile creare un indirizzo con scopo **Fattura**. Se il fornitore verrà pagato con assegni, sarà possibile impostare un indirizzo con lo scopo **Destinazione rimessa**. Se è necessario specificare un indirizzo da utilizzare per trasferire denaro a banche estere, lo scopo sarà **SWIFT**.

## <a name="vendor-contacts"></a>Contatti fornitore
È possibile archiviare i contatti per un fornitore. Tali contatti possono quindi essere utilizzati in diversi documenti, ad esempio ordini fornitore o richieste di offerta.  

Per aggiungere contatti per un fornitore, nella pagina **Tutti i fornitori**, nella scheda **Fornitore**, nel gruppo **Imposta** fare clic su **Contatti** &gt; **Aggiungi contatti**.  

È possibile creare nuovi contatti fornitore. In alternativa, è possibile copiare i dettagli di un'altra persona già registrate in Microsoft Dynamics 365 for Operations e modificare le informazioni in base alle esigenze.  

**Nota:** l'aggiunta del contatto per un fornitore non corrisponde all'aggiunta di informazioni sul contatto per il fornitore. Anche se è possibile aggiungere informazioni di contatto generali per un fornitore, possono essere presenti più persone specifiche come contatti della società, tutte con le proprie informazioni di contatto.  

Non è possibile eliminare un record di contatto se al contatto viene fatto riferimento in un documento. In alternativa, è possibile disattivare il contatto.  

È possibile aggiungere contatti fornitore ai contatti personali in Microsoft Office 365. Tuttavia, è innanzitutto necessario impostare la sincronizzazione tra Dynamics 365 for Operations e Office 365 sia nella sincronizzazione con Microsoft Exchange Server che nell'Installazione guidata di Microsoft Outlook.

## <a name="vendors-in-different-legal-entities"></a>Fornitori in persone giuridiche diverse
Se un fornitore viene registrato solo per una persona giuridica nell'organizzazione e altre persone giuridiche devono registrare lo stesso fornitore, è possibile utilizzare la pagina **Aggiungi fornitore a un'altra persona giuridica** per configurare il fornitore in modo che svolga attività commerciali con un'altra persona giuridica. È necessario selezionare un gruppo di fornitori, la valuta e l'eventuale stato di sospensione del fornitore nella persona giuridica selezionata.  

Se più persone giuridiche nell'organizzazione hanno relazioni commerciali con lo stesso fornitore per il quale ciascuna persona giuridica gestisce un conto fornitore separato, è possibile unire gli ID parte per i conti fornitore. In questo modo, informazioni quali l'indirizzo e il numero di dipendenti possono essere condivise, in modo che sia necessario aggiornarle in un solo punto.  

Per unire gli ID parte, effettuare le seguenti operazioni.

1.  Nella pagina **Rubrica globale** selezionare i record della rubrica che rappresentano il fornitore in ciascuna persona giuridica che si desidera includere nel mapping.
2.  Nel riquadro azioni, fare clic su **Unisci record**.

## <a name="agreements"></a>Contratti
Per impostare un conto fornitore, è inoltre essere necessario registrare gli accordi con il fornitore. È possibile impostare gli accordi su prezzi e sconti utilizzando le operazioni nel record fornitore. È inoltre possibile impostare un contratto di acquisto nella pagina **Contratti di acquisto**.

## <a name="putting-a-vendor-on-hold"></a>Fornitore in attesa
È possibile mettere in attesa un fornitore per vari tipi di transazione. Sono disponibili le seguenti opzioni:

-   **No**: per il fornitore non sono state create sospensioni.
-   **Fattura**: per questo fornitore non è possibile registrare fatture.
-   **Tutto**: il fornitore è sospeso per tutti i tipi di transazione. Questi tipi di transazione includono richieste di acquisto, fatture e pagamenti.
-   **Pagamento**: non è possibile generare pagamenti per il fornitore.
-   **Richiesta**: è possibile creare solo una richiesta di acquisto per volta. Non è possibile creare altre transazioni.
-   **Mai**: il fornitore non viene mai messo in attesa per inattività.

Quando si mette un fornitore in attesa, è possibile specificare un motivo e una data in cui lo stato di attesa verrà terminato. Se non si immette una data di fine, lo stato di attesa del fornitore avrà durata illimitata.

## <a name="vendor-invoice-account"></a>Conto fatture fornitore
Se sono presenti più fornitori con lo stesso indirizzo di fatturazione o se la fatturazione del fornitore avviene tramite terzi, è possibile specificare un conto di fatturazione nel record fornitore. Si tratta del conto a cui viene accreditato l'importo quando si crea una fattura fornitore a partire da un ordine fornitore. Se non si immette un conto fatture sul record fornitore verrà utilizzato in alternativa il conto fornitore.

## <a name="vendor-bank-accounts"></a>Conti bancari fornitore
Se è necessario effettuare i pagamenti a un conto bancario fornitore, è possibile immettere informazioni sulla banca e sui conto bancari del fornitore nella pagina **Conti bancari fornitore**. È inoltre possibile immettere informazioni sulla convalida e sui pagamenti relativi al conto bancario selezionato. Ad esempio, è possibile aggiungere le notifiche anticipate per i conti bancari fornitore. Tali notifiche anticipate vengono utilizzate per verificare l'accuratezza dei dati del conto, ad esempio i numeri di registrazione e i numeri di conto. È necessario specificare un valore predefinito per i pagamenti al fornitore. Tuttavia, quando si effettua un pagamento effettivo, è possibile cambiare questo conto con uno di altri conti fornitore.

## <a name="ledger-accounts"></a>Conti CoGe
È possibile specificare i conti predefiniti visualizzati automaticamente nei giornali di registrazione delle fatture fornitore per il fornitore specificato. Utilizzare questa opzione se in genere si pagano gli stessi tipi di articoli o servizi dagli stessi fornitori nel tempo. Quando si specifica un conto predefinito, è possibile immettere in modo rapido ed efficiente voci nel giornale di registrazione fatture. I conti predefiniti specificati non vengono utilizzati per ordini fornitore o fatture fornitore immesse nella pagina **Fattura fornitore**.  

Selezionare i conti predefiniti nella pagina **Impostazione conto predefinito**, accessibile dalla scheda **Fattura** nel record fornitore. I conti selezionati qui sono visualizzati nell'elenco filtrato dei conti relativi al fornitore quando si effettua un inserimento nel giornale di registrazione. È possibile impostare uno dei conti come conto predefinito.




