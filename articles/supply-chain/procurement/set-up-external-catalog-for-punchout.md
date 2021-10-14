---
title: Configurare un catalogo esterno per PunchOut e-procurement
description: Questo argomento descrive l'utilizzo di un catalogo esterno o PunchOut per raccogliere le informazioni dell'offerta da un fornitore e aggiungerle a una richiesta.
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f1065c68723baa395bc06be6313e45a44661ea3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566914"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>Configurare un catalogo esterno per PunchOut e-procurement

[!include [banner](../includes/banner.md)]

Utilizzando il catalogo esterno, è possibile garantire che le informazioni sul prezzo e sul prodotto che vengono elaborate successivamente in Supply Chain Management siano aggiornate e accurate. La richiesta può quindi essere approvata e convertita in ordine fornitore e l'ordine può essere piazzato al fornitore.

Quando il catalogo esterno viene configurato e un dipendente prepara una richiesta, è disponibile un'opzione per reindirizzare un sito esterno, il catalogo esterno, e restituire il carrello creato nel sito esterno. La comunicazione si basa sul protocollo cXML e deve essere impostata tra i sistemi dell'organizzazione venditrice e acquirente.

Per impostare la comunicazione, il fornitore deve fornire informazioni da utilizzare nella configurazione del catalogo esterno, come l'identità, il dominio della società acquirente, ad esempio "DUNS" e "numero DUNS", le credenziali e l'URL corrispondente al catalogo fornitore.

## <a name="setting-up-an-external-catalog"></a>Impostazione di un catalogo esterno

Il catalogo esterno deve consentire a un dipendente che inserisce una richiesta di acquisto di essere reindirizzato a un sito esterno per selezionare i prodotti. I prodotti che il dipendente seleziona dal catalogo esterno vengono restituiti con le informazioni sui prezzi aggiornate e da qui tali informazioni possono essere aggiunte alla richiesta di acquisto. L'intenzione non è di consentire ai dipendente di piazzare un ordine nel sito esterno. Quando si imposta il catalogo esterno, è necessario assicurarsi che lo scopo del sito a cui si accederà dal catalogo esterno sia di raccogliere le informazioni dell'offerta e non di piazzare un ordine effettivo.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Per impostare un catalogo fornitore esterno, completare le attività elencate di seguito:

1. Impostare una gerarchia di categorie di approvvigionamento. Per ulteriori informazioni, vedere [Impostare criteri per le gerarchie di categorie di approvvigionamento](tasks/set-up-policies-procurement-category-hierarchies.md).
2. Registrare il fornitore in Supply Chain Management. Prima di impostare le configurazioni per accedere al catalogo di un fornitore esterno, è necessario impostare il fornitore e il relativo contatto in Microsoft Dynamics 365. È inoltre necessario aggiungere il fornitore del catalogo esterno alla categoria di approvvigionamento selezionata. Per ulteriori informazioni sulla registrazione di fornitori, vedere [Gestire gli utenti della collaborazione fornitore](manage-vendor-collaboration-users.md) Per informazioni su come assegnare fornitori a una categoria di approvvigionamento, vedere [Approvare i fornitori per categorie specifiche di approvvigionamento](tasks/approve-vendors-specific-procurement-categories.md).
3. Verificare che le unità di misura e la valuta utilizzate dal fornitore siano impostate. Per informazioni su come creare un'unità di misura, vedere [Gestire unità di misura](../pim/tasks/manage-unit-measure.md).
4. Configura il catalogo fornitore esterno utilizzando i requisiti del sito del catalogo del fornitore esterno desiderato. Per ulteriori informazioni su questa attività, vedere [Configurare il catalogo fornitore esterno](#configure-the-external-vendor-catalog).
5. Esegui il test delle configurazioni del catalogo esterno del fornitore per verificare che le impostazioni siano valide e che sia possibile accedere al catalogo esterno del fornitore. Utilizza l'azione **Convalida impostazioni** per convalidare il messaggio di richiesta di impostazione definito. Questo messaggio deve far sì che il sito del catalogo esterno dei fornitori venga aperto in una finestra di browser. Durante la convalida non è possibile ordinare articoli e servizi dal fornitore. Per ordinare articoli e servizi, è necessario accedere al catalogo del fornitore tramite una richiesta di acquisto.
6. Attivare il catalogo esterno utilizzando il pulsante **Attiva catalogo** nella pagina **Cataloghi esterni**. È necessario attivare il catalogo esterno prima che i dipendenti possano utilizzarlo. È possibile disattivare il catalogo esterno in qualsiasi momento.


## <a name="configure-the-external-vendor-catalog"></a>Configurare il catalogo fornitore esterno

In questa sezione vengono forniti ulteriori dettagli sull'attività 4 della sezione precedente.

1. Immetti un nome e una Descrizione per il catalogo esterno del fornitore. Il nome che si inserisce verrà visualizzato nel carrello che rappresenta il catalogo esterno che viene visualizzato ai dipendenti che creano una richiesta. I dipendenti possono fare clic sul carrello per aprire il catalogo nel sito del catalogo esterno del fornitore.
2. Aggiungere un'immagine utilizzando l'azione **Immagine catalogo esterno**. L'immagine verrà visualizzata nel carrello che rappresenta il catalogo esterno che viene visualizzato ai dipendenti che creano una richiesta. Si noti che la larghezza e l'altezza dell'immagine devono essere uguali. In caso contrario l'immagine non viene visualizzata correttamente.
3. Seleziona se il sito Web del catalogo esterno del fornitore deve essere visualizzato nella stessa finestra del browser di quella in cui il dipendente ha creato la richiesta o se deve essere aperto in una nuova finestra.
4. Selezionare il fornitore per il catalogo. Nell'elenco **Persone giuridiche** è presente una riga per ciascuna persona giuridica in cui il fornitore è impostato. Per consentire agli utenti di richiedere prodotti direttamente dal catalogo del fornitore in alcune persone giuridiche ma non in altre, è possibile utilizzare il pulsante **Impedisci accesso** o **Consenti accesso** per ogni persona giuridica in cui si desidera rendere disponibile o meno il catalogo.
5. Nel campo **Scadenza predefinita (in giorni)** immettere il numero di giorni di validità di un'offerta ricevuta dal catalogo esterno e in cui può essere utilizzata per acquistare dal fornitore esterno. Quando un'offerta viene creata e recuperata dal sito del catalogo esterno del fornitore, è valida a partire dalla data di sistema corrente e rimane valida per il numero di giorni immessi in questo campo.
6. Fare clic su **Aggiungi** per iniziare a mappare le categorie di approvvigionamento al catalogo esterno.  Nell'elenco dei nomi di categoria selezionare quindi una categoria. L'elenco di categorie è un soprainsieme di categorie di approvvigionamento a cui il fornitore è stato mappato in tutte le persone giuridiche impostate per il fornitore.

    > [!NOTE]
    > I criteri di approvvigionamento vengono utilizzati per consentire o limitare l'accesso alle categorie per la persona giuridica acquirente o unità operativa ricevente. L'utilizzo di un catalogo esterno richiede che l'accesso sia consentito ad almeno una delle categorie di approvvigionamento mappate al catalogo.

7. Impostare il messaggio di richiesta di impostazione cXML che verrà inviato al fornitore. Il formato del messaggio generato automaticamente è il modello minimo necessario per avviare una sessione. Specificare i valori per i tag.

In qualsiasi momento, è possibile ricaricare il modello del messaggio generato dal sistema facendo clic su **Ripristina formato di messaggio**. Notare che se si ripristina il formato di messaggio, il messaggio corrente verrà sostituito dal formato di messaggio generato automaticamente, che contiene tag vuoti.

### <a name="cxml-setup-message"></a>Messaggio di impostazione cXML
Di seguito è possibile trovare una descrizione dei tag inclusi nel modello:

| Campo | Descrizione | 
|---------|---------|
|< Header >< From >< Credential domain="" >|Dominio della società dell'acquirente.|
|< Header >< From >< Credential>< Identity >< /Identity > | Identità della società dell'acquirente.|
|< Header >< To >< Credential domain="" > | Dominio della società del fornitore.|
|< Header >< To >< Credential>< Identity >< /Identity> | Identità della società del fornitore.|
|< Header >< Sender >< Credential domain="" > | Dominio della società dell'acquirente.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | Identità della società dell'acquirente.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|Segreto condiviso per la società dell'acquirente.|
|< Request deploymentMode=”” >|Distribuzione di test o di produzione.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|URL dell'endpoint PunchOut del fornitore.|

### <a name="extrinsic-elements"></a>Elementi estrinseci

Un elemento estrinseco è un'informazione aggiuntiva, ad esempio un nome utente basato su un utente che esegue l'ordine esterno. L'elemento estrinseco viene impostato quando il si verifica l'operazione PunchOut e può essere inviato nel messaggio di impostazione della richiesta.
Il fornitore potrebbe avere un'esigenza per la ricezione di un elemento estrinseco nella richiesta di impostazione. In tal caso, è necessario aggiungere l'elemento estrinseco all'elenco di elementi estrinseci nella sezione **Formato di messaggio** della pagina **Catalogo esterno**.
Specificare un nome per l'elemento estrinseco che il fornitore può riconoscere e mappare a un valore. Le opzioni per i valori sono: nome utente, posta elettronica dell'utente o valore casuale.
Per ulteriori informazioni sul protocollo cXML, vedere il [sito Web](http://cxml.org/).

## <a name="post-back-message"></a>Messaggio postback
Il messaggio postback è il messaggio che viene ricevuto dal fornitore quando l'utente esegue il check-out dal sito esterno e torna in Supply Chain Management. Non è possibile configurare i messaggi postback. I messaggi sono basati sulla definizione del protocollo cXML. Di seguito sono riportate le informazioni incluse nel messaggio postback che viene ricevuto in una riga di richiesta.

| Messaggio ricevuto dal fornitore | Copiato nella riga di richiesta|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity="" > |Quantità|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|ID articolo esterno|
|< ItemDetail>< UnitPrice >< Money currency="" >| Valuta|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Prezzo unitario|
|< ItemDetail >< Description ShortName="" >|Nome prodotto|
|< ItemDetail >< Description >< /Description >|Incluso nella descrizione dell'articolo; Nome prodotto se ShortName non viene specificato.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Unità|
|< ItemDetail >< Classification >< /Classification >|Incluso nella descrizione articolo|
|< ItemDetail >< Classification domain="" >|Incluso nella descrizione articolo|

## <a name="delete-an-external-catalog"></a>Eliminazione di un catalogo esterno
Eliminare un catalogo esterno all'azione Elimina nella pagina.

Se è stato richiesto un prodotto dal catalogo fornitore esterno, il catalogo non viene eliminato, Lo stato del catalogo esterno viene invece impostato su inattivo. Per rimuovere l'accesso al sito al sito del catalogo esterno del fornitore, senza eliminarlo, imposta lo stato del catalogo esterno su Inattivo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Miglioramenti cXML per gli acquisti](purchasing-cxml-enhancements.md)
- [Usare cataloghi esterni per PunchOut e-procurement](use-external-catalogs-for-punchout.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]