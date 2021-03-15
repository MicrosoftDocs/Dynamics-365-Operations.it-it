---
title: Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento spiega come configurare funzionalità facoltative per un ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993452"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a>Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento spiega come configurare funzionalità facoltative per un ambiente di valutazione Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Prerequisiti

Se si desidera valutare le funzionalità di posta elettronica transazionali, è necessario soddisfare i prerequisiti seguenti:

- Si dispone di un server di posta elettronica disponibile (Serve Simple Mail Transfer Protocol \[SMTP\]), che può essere utilizzato dalla sottoscrizione Microsoft Azure in cui si effettua il provisioning dell'ambiente di valutazione.
- Si dispone del nome di dominio completo (FQDN)/indirizzo IP, numero della porta SMTP e dei dettagli di autenticazione del server.

## <a name="configure-the-image-back-end"></a>Configurare il back-end dell'immagine

### <a name="find-your-media-base-url"></a>Individuare l'URL di base multimediale

> [!NOTE]
> Prima di poter completare questa procedura, è necessario completare i passaggi in [Configura il tuo sito in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).

1. Accedi alla Creazione di siti Web di Commerce utilizzando l'URL di cui hai preso nota quando hai inizializzato l'e-Commerce durante il provisioning (vedere [Inizializzare l'e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Aprire il sito **Fabrikam**.
1. Nel menu a sinistra scegliere **Libreria multimediale**.
1. Selezionare qualsiasi singolo asset di immagine.
1. Nel controllo proprietà a destra, individuare la proprietà **URL pubblico**. Il valore è un URL. Ecco un esempio:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Sostituire l'ultimo identificatore nell'URL (**MA1nQC** nel precedente esempio) con la stringa **search?fileName=**. Ecco come appare l'URL di esempio dopo aver apportato questa modifica:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Questo è l'URL di base multimediale. Prenderne nota.

### <a name="update-the-media-base-url"></a>Aggiornare l'URL di base multimediale

1. Accedere a Commerce headquarters.
1. Utilizzando il menu a sinistra, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Profili canale**.
1. Selezionare **Modifica**.
1. In **Proprietà profilo**, sostituire il valore della proprietà **URL di base server multimediale** con l'URL di base multimediale creato in precedenza.
1. Selezionare il canale denominato **scXXXXXXXXX**.
1. In **Proprietà profilo**, selezionare **Aggiungi**.
1. Per la proprietà che è stata aggiunta, selezionare **URL di base server multimediale** come chiave proprietà. Come valore della proprietà, inserisci l'URL di base multimediale che hai creato in precedenza.
1. Selezionare **Salva**.

## <a name="configure-and-test-the-email-server"></a>Configurare e testare il server di posta elettronica

> [!NOTE]
> il server SMTP o il servizio di posta elettronica specificato qui deve essere accessibile dalla sottoscrizione di Azure utilizzata per l'ambiente.

1. Accedere a Commerce headquarters.
1. Utilizzare il menu a sinistra per selezionare **Moduli \> Retail e Commerce \>  Impostazione sedi centrali \> Parametri \> Parametri posta elettronica**.
1. Nella scheda **Impostazioni SMTP**, nel campo **Server di posta in uscita**, immettere il nome FQDN o l'indirizzo IP del server SMTP o del servizio di posta elettronica.
1. Nel campo **Numero porta SMTP** immettere il numero di porta. (Se non si utilizza Secure Sockets Layer \[SSL\], il numero di porta predefinito è **25** .)
1. Se è richiesta l'autenticazione, immettere i valori nei campi **Nome utente** e **Password**.
1. Selezionare **Salva**.
1. Selezionare **Aggiorna**.
1. Sulla scheda **Messaggio e-mail di prova** nel campo **Provider di posta elettronica**, selezionare **SMTP**.
1. Nel campo **Invia a**, immettere l'indirizzo di posta elettronica a cui inviare il messaggio e-mail di prova.
1. Selezionare **Invia messaggio e-mail di prova**.

## <a name="configure-email-templates"></a>Configurare modelli di messaggi di posta elettronica

Per ciascun evento transazionale per il quale si desidera inviare messaggi di posta elettronica, è necessario aggiornare il modello di messaggio di posta elettronica con un indirizzo di posta elettronica del mittente valido.

1. Accedere a Commerce headquarters.
1. Utilizzare il menu a sinistra per selezionare **Moduli \> Retail e Commerce \>  Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.
1. Selezionare **Mostra elenco**.
1. Per ogni modello dell'elenco, effettuare le operazioni indicate di seguito.

    1. Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.
    1. Facoltativo: nel campo **Nome mittente**, inserire il nome che dovrebbe essere usato come nome del mittente.

1. Selezionare **Salva**.

## <a name="customize-email-templates"></a>Personalizzare i modelli di messaggio di posta elettronica

Potresti voler personalizzare i modelli di messaggio di posta elettronica in modo che utilizzino immagini diverse. Oppure potresti voler aggiornare i collegamenti nei modelli in modo che vadano nell'ambiente di valutazione. Questa procedura illustra come scaricare i modelli predefiniti, personalizzarli e aggiornarli nel sistema.

1. In un browser Web, scaricare il [file ZIP dei modelli di messaggio di posta elettronica predefiniti della valutazione di Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) nel computer locale. Questo file contiene i seguenti documenti HTML:

    - Modello Conferma ordine
    - Modello Emetti gift card
    - Modello Nuovo ordine
    - Modello Ordine di imballaggio
    - Modello Preleva ordine

1. Personalizzare i modelli utilizzando un editor di testo o HTML. Vedere l'elenco dei [token supportati](#supported-tokens-in-the-email-template) più avanti in questo argomento.
1. Accedere a Commerce.
1. Utilizzare il menu a sinistra per selezionare **Moduli \> Amministrazione organizzazione \> Impostazione \> Modelli di posta elettronica a livello di organizzazione**.
1. Espandere l'elenco a sinistra per visualizzare tutti i modelli.
1. Per ogni modello che si desidera personalizzare, attenersi alla seguente procedura:

    1. Selezionare il modello nell'elenco.
    1. In **Contenuto messaggio posta elettronica**, selezionare la versione appropriata della lingua nell'elenco. Il valore predefinito della lingua è **en-us**.
    1. In **Contenuto messaggio posta elettronica**, selezionare **Modifica**. Viene visualizzato il riquadro **Carica modello di messaggio di posta elettronica**.
    1. Selezionare **Sfoglia** e trovare il file HTML con il contenuto personalizzato.
    1. Selezionare **Carica**. Il modello viene caricato nel sistema e viene visualizzata un'anteprima.
    1. Selezionare **OK**.
    1. Facoltativo: Personalizzare la proprietà **Oggetto** del modello.
    1. Selezionare **Salva**.

### <a name="supported-tokens-in-the-email-template"></a>Token supportati nel modello di messaggio di posta elettronica

Durante il rendering del messaggio di posta elettronica questi token verranno sostituiti con i valori effettivi applicabili al cliente e al relativo ordine.

#### <a name="sales-order"></a>Ordine cliente

I token seguenti si applicano a tutti gli ordini cliente.

| Nome del token | Token  |
|-------------------|-------|
| Numero ordine      | %salesid% |
| Nome cliente   | %customername% |
| Indirizzo di consegna  | %deliveryaddress% |
| Indirizzo di fatturazione   | %customeraddress% |
| Data ordine        | %shipdate% |
| Modalità di consegna     | %modeofdelivery% |
| Sconto          | %discount% |
| IVA         | %tax% |
| Totale ordine       | %total% |

#### <a name="sales-line"></a>Riga di vendita

I seguenti token vengono sostituiti con i valori di ogni prodotto nell'ordine.

> [!NOTE]
> Inserire il token **Elenco prodotti - Inizio** all'inizio del blocco HTML che si ripete per ogni prodotto e inserire il token **Elenco prodotti - Fine** alla fine del blocco.

| Nome del token      | Token |
|------------------------|-------|
| Elenco prodotti - Inizio   | \<!--%tablebegin.salesline% --\> |
| Elenco prodotti - Fine     | \<!--%tableend.salesline%--\> |
| Nome prodotto           | %lineproductname% |
| descrizione            | %lineproductdescription% |
| Quantità               | %linequantity% |
| Riga prezzo unitario        | %lineprice% (verify) |
| Totale voci        | %linenetamount% |
| Riga sconto          | %linediscount% |
| Data di spedizione              | %lineshipdate% |
| Metodo di approvvigionamento     | %linedeliverymode% |
| Indirizzo di consegna       | %linedeliveryaddress% |
| Unità di vendita della riga | %lineunit% |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di valutazione Dynamics 365 Commerce](cpe-overview.md)

[Provisioning di un ambiente di valutazione Dynamics 365 Commerce](provisioning-guide.md)

[Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce](cpe-bopis.md)

[Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]