---
title: Domande frequenti sulla rubrica
description: 
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 960e2cfac8b770f0e9e4d1e4136e6005ee3a0c7d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="address-books-faq"></a>Domande frequenti sulla rubrica

[!include[banner](../includes/banner.md)]




<a name="how-do-i-check-for-duplicate-records"></a>Come si controlla se sono presenti record duplicati?
-------------------------------------

È possibile controllare la presenza di record duplicati direttamente dalla pagina elenco **Rubrica globale**. Nella scheda **Parte** del riquadro azioni, nel gruppo **Gestisci** fare clic su **Controlla duplicati**. Selezionare quindi i valori da includere nella verifica dei duplicati.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>È possibile aggiungere o eliminare i record di parti dalla Rubrica?
Sì, è possibile aggiungere più record di parti a una Rubrica e rimuovere più record di parti.

-   Per aggiungere più record di parti a una Rubrica, **Rubrica globale** nella pagina elenco, selezionare le parti nell'elenco. Nella scheda **Parti** del riquadro azioni, nel gruppo **Gestisci** fare clic su **Assegna parti**. Selezionare le rubriche a cui aggiungere i record di parti selezionati, quindi fare clic su **OK**. Tutti i record di parti selezionati vengono aggiunti alle rubriche selezionate.
-   Per rimuovere più record di parti da una Rubrica, nella pagina elenco **Rubrica globale**, selezionare le parti nell'elenco. Nella scheda **Parti** del riquadro azioni, nel gruppo **Gestisci** fare clic su **Rimuovi parti**. Selezionare le rubriche da cui rimuovere le parti e fare clic su **OK**. Tutti i record di parti selezionati vengono rimossi dalle rubriche selezionate.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Posso modificare il tipo di parte di un record o devo eliminare il record precedente e crearne uno nuovo?
Occasionalmente potrebbe essere necessario modificare il tipo di parte di un record da persona a organizzazione o da organizzazione a persona. Ad esempio, Nancy è un membro del team di vendita per Fabrikam U.K.. Durante una fiera commerciale a Londra, incontra sei nuovi prospect. Nancy creare un record parte per ciascun prospect. Quando Nancy salva i record, questi verranno creati anche nella rubrica globale. Fabrikam ha il tipo predefinito di parte impostato su organizzazione, ma due dei nuovi prospect devono avere un tipo di record persona. Pertanto, quando Nancy torna dalla fiera, deve modificare il tipo di parte dei due record prospect. Per modificare un record parte da un tipo di parte a un altro, è necessario innanzitutto creare un nuovo record parte del tipo corretto nella rubrica globale. Quindi associare il record parte precedente al nuovo record. Dopo avere effettuato la nuova associazione di parte, eliminare il record parte originale con il tipo di record errato.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Come si modifica il nome o l'indirizzo di un record di parti?
È possibile aggiornare il nome di un record di parti e gli indirizzi associati al record, in qualsiasi momento.

-   Per aggiornare il nome di un record di parti, aprire il record di parti, quindi nel Riquadro azioni, fare clic su **Modifica**. Nella Scheda dettaglio **Generale** immettere il nuovo nome per la parte quindi salvare il record.
-   Per aggiornare un indirizzo per un record parte, aprire il record parte, quindi nella Scheda dettaglio **Indirizzi** selezionare l'indirizzo da aggiornare. Fare clic su **Modifica** quindi nella pagina **Modifica indirizzo**, fare le modifiche necessarie all'indirizzo o i parametri di indirizzo.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>È possibile unire due o più record di parti in un record?
Talvolta può essere opportuno unire due o più record di parti in un singolo record, ad esempio in caso di creazione intenzionale o involontaria di uno o più record di parti duplicati. Se si uniscono record di parti, viene selezionato un record da mantenere. Le informazioni dell'altro record verranno unite a quelle del primo record. Ad esempio, le informazioni relative a Fabrikam sono archiviate in tre record di parti, A, B e C. L'utente sceglie di mantenere il record di parti A. Le informazioni archiviate nei record di parti B e C verranno pertanto unite nel record A. In alcuni casi non è possibile unire i record di parte:

-   Non è possibile unire record di parti associati allo stesso ruolo della parte, ad esempio un cliente o un fornitore, nella stessa persona giuridica. La parte A è ad esempio associata a un cliente nella persona giuridica 123 e la parte B è associata a un altro cliente nella persona giuridica 123. Non è possibile unire questi record di parti, in quanto se fossero uniti il record unito verrebbe associato a più clienti nella stessa persona giuridica e questo non è consentito. I record potranno tuttavia essere uniti se la parte B è associata a un fornitore nella persona giuridica 123 o a un cliente in un'altra persona giuridica.
-   Non è possibile unire record di organizzazioni di parti interne nella stessa persona giuridica, team o unità operativa.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>È necessario creare un record di parti nella Rubrica globale o in un'altra posizione, ad esempio la pagina cliente o fornitore?
È possibile immettere i record di parti nella Rubrica globale o nella pagina appropriata della persona giuridica. Quando si aggiunge un record in un'ubicazione, lo stesso record viene aggiunto sempre in un'altra posizione. Ad esempio, se si aggiunge un record parte di un cliente nella Rubrica globale, il record viene anche aggiunto alla pagina **Cliente**. Allo stesso modo, se si aggiunge un record parte di un cliente nella pagina **Cliente** il record viene aggiunto anche alla rubrica globale. Utilizzare le seguenti indicazioni per decidere se è necessario immettere nuovi record di parti:

-   **Creazione di un record parte quando non si conosce il tipo di entità:** se è necessario creare un record parte e non si conosce il tipo di entità, ad esempio non si sa se l'entità è un cliente o un'opportunità, creare il record nella rubrica globale. È possibile selezionare il tipo di entità successivamente.
-   **Creazione di un record parte quando si conosce il tipo di entità**: se si conosce il tipo di entità della parte, è possibile creare un record nel modulo pertinente per tale tipo. Ad esempio, per un cliente, creare un record per un cliente nella pagina **Cliente**. Quando si crea e si salva un record mediante la pagina entità appropriata, il record verrà creato automaticamente nella rubrica globale.

## <a name="can-i-translate-address-information-for-party-records"></a>È possibile tradurre le informazioni relative all'indirizzo per record di parti?
È possibile impostare le traduzioni delle informazioni relative all'indirizzo in modo che vengano visualizzate nella lingua dell'utente (lingua del sistema) in Microsoft Dynamics 365 for Finance and Operations, ma in un'altra lingua nei documenti, ad esempio ordini cliente. È possibile immettere traduzioni per i nomi dei paesi, gli scopi di indirizzo e le sequenze nome. Ad esempio, la lingua del sistema è danese e viene creato un ordine cliente per un cliente in Francia. In questo caso, è possibile visualizzare il record cliente in Danese nel programma ma visualizzare le informazioni relative all'indirizzo nell'ordine cliente stampato. Quando vengono impostate le traduzioni, è necessario immetterne una per ogni elemento nell'elenco. Tutti gli articoli per cui non si immette una traduzione appariranno nella lingua del sistema. Ad esempio, la lingua del sistema è danese e viene inviato un documento a un cliente in Spagna. Se non sono state immesse le traduzioni spagnole per le informazioni sull'indirizzo, queste verranno visualizzate in Danese sia nel programma sia nel documento stampato.




