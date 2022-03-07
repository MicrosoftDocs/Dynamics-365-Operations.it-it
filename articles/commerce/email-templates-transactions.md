---
title: Crea modelli e-mail per eventi transazionali
description: Questo argomento descrive come creare, caricare e configurare modelli e-mail per eventi transazionali in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4fd46ea161fb4441d94a9e7c7f7ffbfb245eb873
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919503"
---
# <a name="create-email-templates-for-transactional-events"></a>Creare modelli e-mail per eventi transazionali

[!include [banner](includes/banner.md)]


Questo argomento descrive come creare, caricare e configurare modelli e-mail per eventi transazionali in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce fornisce una soluzione pronta all'uso per l'invio di e-mail che avvisano i clienti di eventi transazionali. Ad esempio, le e-mail possono essere inviate quando un ordine viene effettuato, è pronto per il ritiro o è stato spedito. Questo argomento descrive i passaggi per la creazione, il caricamento e la configurazione dei modelli e-mail utilizzati per inviare e-mail transazionali.

## <a name="notification-types"></a>Tipi di notifiche

Le notifiche possono essere configurate per informare i clienti via e-mail quando si verificano eventi specifici come parte dell'ordine e del ciclo di vita del cliente. Per configurare le notifiche, devi associare un modello di e-mail a un tipo di notifica creando un profilo di notifica e-mail Commerce. Per informazioni su come impostare i profili di notifica e-mail, vedi [Configura un profilo di notifica e-mail](email-notification-profiles.md).

Dynamics 365 Commerce supporta i seguenti tipi di notifica.

### <a name="order-created"></a>Ordine creato

Il tipo di notifica *ordine creato* viene attivato quando viene creato un nuovo ordine di vendita in Commerce headquarters.

> [!NOTE]
> Il tipo di notifica creato dall'ordine non viene attivato per le transazioni cash-and-carry che si verificano in un terminale POS (Point of Sale). In questo caso, viene invece generata una ricevuta inviata via e-mail e/o stampata. Per ulteriori informazioni, vedi [Invia ricevute e-mail da Modern POS (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Ordine confermato

Il tipo di notifica *ordine confermato* viene attivato quando viene generato un documento di conferma dell'ordine per un ordine di vendita da Commerce headquarters.

### <a name="picking-completed"></a>Prelievo completato

Il tipo di notifica *prelievo completato* viene attivato quando una distinta di prelievo per un ordine viene contrassegnata come completata in Commerce headquarters.

> [!NOTE]
> Il tipo di notifica di prelievo completato non viene attivato quando un articolo viene contrassegnato come prelevato presso un terminale POS.

### <a name="packing-completed"></a>Imballaggio completato

Il tipo di notifica *prelievo completato* viene attivato quando un documento di trasporto viene generato per un ordine in Commerce headquarters a un terminale POS.

Il tipo di notifica prelievo completato supporta i seguenti segnaposto e-mail aggiuntivi per facilitare la funzionalità "ordine pronto per il ritiro" e la ricerca dell'ordine dalle e-mail transazionali.

| Nome segnaposto    | Scopo |
| ------------------- | ------- |
| `pickupstorename`     | Il nome del negozio in cui l'ordine è disponibile per il ritiro. |
| `pickupstoreaddress`  | L'indirizzo del negozio in cui l'ordine è disponibile per il ritiro. |
| `pickupstorehourfrom` | L'orario di apertura del punto vendita. |
| `pickupstorehourto`   | L'orario di chiusura del punto vendita. |
| `pickupchannelid`     | L'ID del canale del negozio di ritiro. |
| `packingslipid`      | L'ID del documento di trasporto per l'ordine che verrà ritirato. |
| `confirmationid`      | L'ID di conferma dell'ordine che verrà ritirato. Questo ID è talvolta indicato come ID di riferimento del canale. |

Per ulteriori informazioni sulle funzioni di check-in dei clienti e ricerca degli ordini, vedi [Impostare il rilevamento geografico e il reindirizzamento](geo-detection-redirection.md) e [Abilitare la ricerca degli ordini per checkout guest](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Ordine pronto per il prelievo

Il tipo di notifica *ordine pronto per il ritiro* viene attivato quando un ordine è contrassegnato come imballato e la modalità di consegna è impostata su **Ritiro del cliente** su una o più righe dell'ordine.

> [!NOTE]
> Il tipo di notifica di ordine pronto per il ritiro è stato ritirato a favore del tipo di notifica di imballaggio completato. Questo tipo di notifica è personalizzato in base alla modalità di consegna.

### <a name="order-shipped"></a>Ordine spedito

Il tipo di notifica *ordine spedito* viene attivato quando viene fatturato un ordine che ha una modalità di consegna senza ritiro in negozio.

> [!NOTE]
> Il tipo di notifica ordine spedito per il ritiro è stato ritirato a favore del tipo di notifica ordine fatturato. Questo tipo di notifica è personalizzato in base alla modalità di consegna.

### <a name="order-invoiced"></a>Ordine fatturato

Il tipo di notifica *ordine fatturato* viene attivato quando un ordine viene fatturato in POS o Commerce headquarters.

### <a name="issue-gift-card"></a>Emetti gift card

Il tipo di notifica *emetti gift card* viene attivato quando viene fatturato un ordine di vendita che contiene un prodotto del tipo buono regalo.

> [!NOTE]
> L'e-mail di notifica del problema relativo alla gift card viene inviata al destinatario della gift card. Il destinatario della gift card è specificato in Commerce headquarters, su una singola riga dell'ordine di vendita nella scheda **Imballaggio** in **Dettagli riga**. Può essere specificato manualmente oa livello di codice.

Il tipo di notifica Emetti gift card supporta i seguenti segnaposto aggiuntivi.

| Nome segnaposto      | Scopo |
| --------------------- | ------- |
| `giftcardnumber`        | Il numero della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardbalance`       | Il saldo della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardmessage`       | Il messaggio della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardpin`         | Il PIN (numero di identificazione personale) della carta regalo, per i prodotti del tipo di carta regalo. Questo segnaposto è specifico per le carte regalo esterne. |
| `giftcardexpiration`    | La data di scadenza della carta regalo, per i prodotti del tipo di carta regalo. Questo segnaposto è specifico per le carte regalo esterne. |
| `giftcardrecipientname` | La nome del destinatario della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardbuyername`     | La nome dell'acquirente della carta regalo, per i prodotti del tipo di carta regalo. |

Per ulteriori informazioni sulle gift card, vedi [Gift card digitali per l'e-commerce](digital-gift-cards.md) e [Supporto per gift card esterne](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Annullamento ordine

Il tipo di notifica *cancellazione ordine* viene attivato quando un ordine viene cancellato in Commerce headquarters.

### <a name="customer-created"></a>Cliente creato

Il tipo di notifica *cliente creato* viene attivato quando viene creata una nuova entità cliente in Commerce headquarters.

### <a name="b2b-prospect-approved"></a>Prospect B2B approvato

Il tipo di notifica *Prospect B2B approvato* viene attivato quando la richiesta di onboarding di un potenziale cliente viene approvata in Commerce headquarters. Per ulteriori informazioni su come approvare o rifiutare potenziali clienti B2B, vedi [Impostare l'utente amministratore per un nuovo partner commerciale](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Il tipo di notifica Prospect B2B approvato supporta i seguenti segnaposto aggiuntivi.

| Nome segnaposto | Scopo                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | Il nome del potenziale cliente B2B così come è stato inserito nell'applicazione. |
| `lastname`         | Il cognome del potenziale cliente B2B così come è stato inserito nell'applicazione. |
| `company`          | Il nome dell'azienda del candidato così come è stato inserito nell'applicazione. |
| `email`            | L'indirizzo e-mail del potenziale cliente così come è stato inserito nell'applicazione.   |
| `zipcode`          | Il CAP dell'indirizzo principale del potenziale cliente. |
| `comments`         | Il commento che il potenziale cliente ha inserito nella domanda. |
| `storename`        | Il nome del canale in cui è stato creato il potenziale cliente. |
| `storeurl`         | Vuoto per impostazione predefinita. È necessario creare un'estensione personalizzata per utilizzare questo segnaposto. |

### <a name="b2b-prospect-rejected"></a>Prospect B2B rifiutato

Il tipo di notifica *Prospect B2B rifiutato* viene attivato quando la richiesta di onboarding di un potenziale cliente viene rifiutata in Commerce headquarters. Per ulteriori informazioni su come approvare o rifiutare potenziali clienti B2B, vedi [Impostare l'utente amministratore per un nuovo partner commerciale](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

Il tipo di notifica Prospect B2B rifiutato supporta i seguenti segnaposto aggiuntivi.

| Nome segnaposto | Scopo                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | Il nome del potenziale cliente B2B così come è stato inserito nell'applicazione. |
| `lastname`         | Il cognome del potenziale cliente B2B così come è stato inserito nell'applicazione. |
| `company`          | Il nome dell'azienda del candidato così come è stato inserito nell'applicazione. |

## <a name="create-an-email-template"></a>Crea un modello di messaggio di posta elettronica

Prima di poter mappare un evento transazionale specifico a un modello e-mail, devi creare il modello.

Per creare un modello e-mail attenersi alla procedura seguente.

1. In Commerce Headquarters, selezionare **Retail e Commerce \> Impostazione sedi centrali \> Modelli di posta elettronica a livello di organizzazione** o **Amministrazione organizzazione \> Impostazione \> Modelli di posta elettronica a livello di organizzazione**.
1. Selezionare **Nuovo**.
1. In **Generale**, imposta i seguenti campi:

    - **ID e-mail**: l'ID e-mail è l'identificatore univoco per un modello. È il valore che viene mostrato quando selezioni un modello da mappare a un evento.
    - **Descrizione e-mail**: puoi utilizzare questo campo opzionale per fornire una descrizione del modello. Il valore inserito viene visualizzato solo in Commerce headquarters.
    - **Nome mittente**: il nome inserito viene visualizzato nel campo "da" della maggior parte dei client e-mail.
    - **Indirizzo di posta elettronica del mittente**: immetti l'indirizzo e-mail da utilizzare per le e-mail inviate utilizzando questo modello.
    - **Codice lingua predefinito**: questo campo specifica la versione localizzata dell'e-mail che viene inviata per impostazione predefinita, se non viene fornita alcuna lingua dal canale che invoca questo modello.

1. In **Contenuto messaggio posta elettronica**, seleziona **Nuovo**.
1. Nel campo **Lingua**, inserisci la lingua per il modello e-mail. Puoi aggiungere più lingue e modelli localizzati in un secondo momento.
1. Nel campo **Oggetto**, inserisci l'oggetto dell'e-mail che dovrebbe apparire nel campo dell'oggetto dell'e-mail.
1. Seleziona **Modifica** per caricare il tuo modello e-mail.

## <a name="create-an-email-message-body-by-using-html"></a>Crea un corpo di un messaggio e-mail utilizzando HTML

Il corpo del messaggio della tua e-mail è composto in HTML. Puoi utilizzare qualsiasi layout, stile e marchio HTML e fogli CSS (Cascading Style Sheets) consentiti. Puoi inoltre utilizzare le immagini, se le ospiti su un endpoint Web disponibile pubblicamente. Per aggiungere un'immagine, inserisci l'URL dell'immagine nell'attributo **src** dell'etichetta HTML **&lt;img&gt;**.

> [!NOTE]
> I client e-mail impongono limiti di layout e stile che potrebbero richiedere modifiche al codice HTML e CSS che usi per il corpo del messaggio. Si consiglia di familiarizzare con le migliori pratiche per la creazione di HTML che i client di posta elettronica più popolari supportano.

## <a name="add-placeholders-to-the-email-message-body"></a>Aggiungi segnaposti al corpo del messaggio e-mail

La tua e-mail può contenere segnaposti che vengono sostituiti con valori specifici del cliente e specifici della transazione quando viene generata l'e-mail. I segnaposti sono sempre circondati da segni di percentuale (%) e vengono inseriti direttamente nel documento HTML.

Ecco un esempio.

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Segnaposti ordini (livello ordine cliente)

I seguenti segnaposto recuperano e mostrano i dati definiti a livello di ordine cliente (anziché a livello di linea di vendita).

| Nome segnaposto     | Scopo                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | Il nome del cliente che ha emesso l'ordine.               |
| `customeraddress`      | L'indirizzo del cliente.                                 |
| `customeremailaddress` | L'indirizzo e-mail che il cliente ha inserito al momento del pagamento.     |
| `salesid`              | L'ID delle vendite dell'ordine.                                   |
| `orderconfirmationid`  | ID multicanale generato durante la creazione dell'ordine.   |
| `channelid`            | ID del canale di vendita al dettaglio o online attraverso il quale è stato effettuato l'ordine. |
| `deliveryname`         | Nome specificato per l'indirizzo di consegna.         |
| `deliveryaddress`      | L'indirizzo di consegna per gli ordini spediti.                     |
| `deliverydate`         | La data di consegna.                                           |
| `shipdate`             | La data di spedizione.                                               |
| `modeofdelivery`       | La modalità di consegna dell'ordine.                              |
| `ordernetamount`       | L'importo totale per l'ordine, meno l'imposta totale.         |
| `discount`            | Lo sconto totale per l'ordine.                            |
| `charges`              | Le spese totali per l'ordine.                             |
| `tax`                  | L'imposta totale per l'ordine.                                 |
| `total`                | L'importo totale per l'ordine.                              |
| `storename`            | Il nome del negozio dove è stato effettuato l'ordine.            |
| `storeaddress`         | L'indirizzo del negozio dove è stato effettuato l'ordine.              |
| `storeopenfrom`        | L'orario di apertura del negozio dove è stato effettuato l'ordine.         |
| `storeopento`          | L'orario di chiusura del negozio dove è stato effettuato l'ordine.         |
| `pickupstorename`      | Il nome del negozio in cui verrà ritirato l'ordine.\*   |
| `pickupstoreaddress`   | L'indirizzo del negozio in cui verrà ritirato l'ordine.\* |
| `pickupopenstorefrom`  | L'orario di apertura del negozio in cui verrà ritirato l'ordine.\* |
| `pickupopenstoreto`    | L'orario di chiusura del negozio in cui verrà ritirato l'ordine.\* |
| `pickupchannelid`     | ID canale del punto vendita specificato per una modalità di consegna con ritiro.\* |
| `packingslipid`        | ID del documento di trasporto generato quando le righe di un ordine sono state imballate.\* |

\* Questi segnaposto restituiscono i dati solo quando vengono utilizzati per il tipo di modifica **Ordine pronto per il ritiro**. 

### <a name="order-line-placeholders-sales-line-level"></a>Segnaposti righe ordini (livello riga cliente)

I seguenti segnaposti recuperano e mostrano i dati per i singoli prodotti (righe) nell'ordine cliente.

| Nome segnaposto               | Scopo |
|--------------------------------|-------------------|
| `productid`                      | <p>ID del prodotto. Questo ID tiene conto delle varianti.</p><p><strong>Nota:</strong> questo segnaposto è stato deprecato a favore di `lineproductrecid`.</p> |
| `lineproductrecid`               | ID del prodotto. Questo ID tiene conto delle varianti. Identifica in modo univoco un articolo a livello di variante. |
| `lineitemid`                     | ID del prodotto (questo ID non tiene conto delle varianti). |
| `lineproductvariantid`           | ID della variante prodotto. |
| `lineproductname`                | Nome del prodotto. |
| `lineproductdescription`         | La descrizione del prodotto. |
| `linequantity`                   | Il numero di unità che sono state ordinate per la riga, più l'unità di misura (ad esempio, **unità** o **coppia**). |
| `lineunit`                       | L'unità di misura per la riga. |
| `linequantity_withoutunit`       | Il numero di unità che sono state ordinate per la riga, senza l'unità di misura. |
| `linequantitypicked`             | Quando viene utilizzato l'evento **PickOrder**, il numero di unità selezionate. Altrimenti, **0** (zero). |
| `linequantitypicked_withoutunit` | Quando viene utilizzato l'evento **PickOrder**, il numero di unità selezionate, senza l'unità di misura. Altrimenti, **0** (zero). |
| `linequantitypacked`             | Quando vengono utilizzati gli eventi **PackOrder** e **Ordine pronto per il prelievo**, il numero di unità che sono state imballate. Altrimenti, **0** (zero). |
| `linequantitypacked_withoutuom`  | Quando vengono utilizzati gli eventi **PackOrder** e **Ordine pronto per il prelievo**, il numero di unità che sono state imballate, senza l'unità di misura. Altrimenti, **0** (zero). |
| `linequantityshipped`            | Sempre **0**, tranne quando vengono utilizzati eventi specifici, come descritto nella riga successiva. |
| `linequantityshipped_withoutuom` | Quando viene utilizzato l'evento **ShipOrder**, il numero di unità selezionate, senza l'unità di misura. Altrimenti, **0** (zero). |
| `lineprice`                      | Prezzo di una singola unità. |
| `linenetamount`                  | Il prezzo della riga dopo l'applicazione del numero di unità e dello sconto. |
| `linediscount`                   | Lo sconto per una singola unità. |
| `lineshipdate`                   | La data di spedizione della riga. |
| `linedeliverydate`               | La data di consegna della riga. |
| `linedeliverymode`               | La modalità di consegna della riga. |
| `linedeliveryaddress`            | L'indirizzo di consegna della riga. |
| `linepickupdate`                 | La data di ritiro specificata dal cliente per gli ordini che utilizzano una modalità di consegna con ritiro. |
| `linepickuptimeslot`             | L'intervallo di tempo di ritiro specificato dal cliente per gli ordini che utilizzano una modalità di consegna con ritiro. |
| `giftcardnumber`                 | Il numero della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardbalance`                | Il saldo della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardmessage`                | Il messaggio della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardpin`                    | Il PIN della gift card, per i prodotti del tipo di carta regalo. Questo segnaposto è specifico per le carte regalo esterne. |
| `giftcardexpiration`             | La data di scadenza della carta regalo, per i prodotti del tipo di carta regalo. Questo segnaposto è specifico per le carte regalo esterne. |
| `giftcardrecipientname`          | La nome del destinatario della carta regalo, per i prodotti del tipo di carta regalo. |
| `giftcardbuyername`              | La nome dell'acquirente della carta regalo, per i prodotti del tipo di carta regalo. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Formato dei segnaposto della riga ordine nel corpo del messaggio e-mail

Quando si crea l'HTML per le singole righe dell'ordine nel corpo del messaggio e-mail, circondare il blocco ripetuto di HTML e i segnaposto per le righe con i seguenti segnaposto. Notare che i segnaposto si trovano all'interno dei tag di commento HTML.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

Ecco un esempio.

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Crea un modello per le ricevute inviate via e-mail

Le ricevute possono essere inviate via e-mail ai clienti che effettuano acquisti presso un punto vendita al dettaglio (POS). In generale, i passaggi per la creazione del modello di ricevuta inviato tramite e-mail sono gli stessi della creazione di modelli per altri eventi transazionali. Tuttavia, sono necessarie le seguenti modifiche:

- Il segnaposto **%message%** viene usato per inserire il testo della ricevuta nell'e-mail. Per assicurarsi il rendering corretto del corpo della ricevuta, circondare il segnaposto **%message%** con tag **&lt;pre&gt;** e **&lt;/pre&gt;** HTML.
- Il segnaposto **%receiptid%** può essere utilizzato per mostrare un codice a matrice o un codice a barre che rappresenta l'ID ricevuta. (i codici a matrice e i codici a barre vengono generati dinamicamente e forniti da un servizio di terze parti). Per ulteriori informazioni su come mostrare un codice a matrice o un codice a barre in una ricevuta inviata tramite e-mail, vedere [Aggiungere un codice a matrice o un codice a barre ai messaggi di posta elettronica transazionali e di ricevuta](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Carica l'e-mail in formato HTML

Dopo aver creato e testato l'HTML per il corpo del messaggio, devi caricarlo in Commerce headquarters. Attualmente, l'email HTML non può essere esportata. Pertanto, devi conservare la copia originale del codice HTML fuori da Commerce headquarters.

Per caricare un modello e-mail HTML nuovo o modificato, attieniti alla seguente procedura.

1. In Commerce headquarters, vai a **Retail e Commerce \> Impostazione sedi centrali \> Modelli di posta elettronica a livello di organizzazione**.
1. Seleziona la riga per la lingua a cui desideri aggiungere o sostituire l'HTML. In alternativa, seleziona **Nuovo** per creare una riga per una nuova lingua.
1. Selezionare **Modifica**.
1. Nella finestra di dialogo visualizzata, seleziona **Sfoglia**. Accedi al documento HTML che desideri caricare, selezionalo, quindi seleziona **Apri**.
1. Selezionare **Carica**.
1. Dopo che l'e-mail HTML viene visualizzata nella finestra di anteprima, seleziona **OK**.
1. Verifica che la casella di spunta **Con corpo** sia selezionata per la riga.

Se hai già configurato Commerce headquarters per l'invio di e-mail, la tua e-mail nuova o aggiornata verrà inviata a tutti i clienti che eseguono una transazione che richiama l'evento mappato al modello.

Per ulteriori informazioni su come configurare le e-mail in Dynamics 365 Commerce, vedi [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Risorse aggiuntive 

[Impostare un profilo di notifica tramite posta elettronica](email-notification-profiles.md)

[Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Impostare ricevute tramite posta elettronica](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Inviare le ricevute tramite posta elettronica da Modern POS ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
