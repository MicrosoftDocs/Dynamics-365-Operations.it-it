---
title: Gift card digitali per l'e-commerce
description: Questo argomento descrive il funzionamento delle gift card digitali nell'implementazione dell'e-commerce di Microsoft Dynamics 365 Commerce. Fornisce inoltre una panoramica di importanti passaggi di configurazione.
author: anupamar-ms
ms.date: 05/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: de8811b3265bc582a055aaad1f3dea32def552f4
ms.sourcegitcommit: d38d2fe85dc2497211ba5731617f590029d07145
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809589"
---
# <a name="e-commerce-digital-gift-cards"></a>Gift card digitali per l'e-commerce

[!include [banner](includes/banner.md)]

Questo argomento descrive il funzionamento delle gift card digitali nell'implementazione dell'e-commerce di Microsoft Dynamics 365 Commerce. Fornisce inoltre una panoramica di importanti passaggi di configurazione.

In Dynamics 365 Commerce, l'acquisto di gift card digitali segue lo stesso flusso dell'acquisto di altri prodotti nel sistema. Non è necessario configurare moduli aggiuntivi. Se al carrello vengono aggiunte più gift card, le voci gift card non vengono aggregate in una singola riga di vendita. Questo comportamento è necessario perché ogni riga di vendita viene fatturata utilizzando un numero di gift card separato.

L'acquisto di gift card digitali è supportato in Dynamics 365 Commerce versione 10.0.16 e successive.

La figura seguente mostra un esempio della pagina dei dettagli del prodotto (PDP) per una gift card digitale sul sito di e-commerce Fabrikam.

![Esempio di PDP di una gift card digitale sul sito e-commerce di Fabrikam.](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Attivare la funzionalità delle gift card digitali in Commerce headquarters

Affinché il flusso di acquisto delle gift card digitali funzioni in Dynamics 365 Commerce, la funzione **Acquisto di gift card in e-commerce** deve essere attivata in Commerce headquarters. Puoi trovare la funzione nell'area di lavoro **Gestione funzionalità** in Commerce headquarters, come mostrato nell'illustrazione seguente.

![Area di lavoro Gestione funzionalità in Commerce headquarters.](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Configurare una gift card digitale in Commerce headquarters

I prodotti della gift card digitale devono essere configurati in Commerce headquarters. Il processo è analogo a quello per gli altri prodotti. Tuttavia, i seguenti passaggi importanti sono specifici per la configurazione delle gift card per l'acquisto. Per ulteriori informazioni su come creare e configurare i prodotti, vedi [Creare un nuovo prodotto in Commerce](create-new-product-commerce.md).

- Quando configuri i prodotti delle gift card digitali nella finestra di dialogo **Nuovo prodotto** imposta il campo **Tipo di prodotto** su **Servizio**. (Per aprire la finestra di dialogo, vai a **Retail e Commerce \> Prodotti e categorie \> Prodotti per categoria** e seleziona **Nuovo**). I prodotti di tipo **Servizio** non vengono controllati per l'inventario disponibile prima che venga effettuato un ordine. Per ulteriori informazioni, vedi [Creare un nuovo prodotto](create-new-product-commerce.md#create-a-new-product).
- Nella pagina **Parametri di Commerce** nella scheda **Registrazione**, il campo **Prodotto gift card** deve essere impostato su **Gift card digitale**, come mostrato nell'illustrazione seguente. Se il prodotto è una gift card esterna, vedi [Supporto per gift card esterne](./dev-itpro/gift-card.md) per maggiori informazioni.

    ![Campo del prodotto gift card in Commerce headquarters.](./media/PostGiftcard.png)

- Se una gift card deve supportare più importi predefiniti (ad esempio, $25, $50 e $100), il campo **Dimensioni** deve essere utilizzato per impostare tali importi predefiniti. Ogni importo predefinito sarà una variante di prodotto. Per ulteriori informazioni sulle dimensioni prodotto, vedi [Dimensioni del prodotto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Se i clienti devono essere in grado di specificare un importo personalizzato per una gift card oltre agli importi predefiniti, imposta prima una variante che consenta un importo personalizzato. L'attributo **Dimensione** supporta le varianti di importo personalizzate. Quindi, apri il prodotto dalla pagina **Prodotti rilasciati nella categoria** quindi nella scheda dettaglio **Commerce** imposta il campo **Specifica prezzo** su **È necessario digitare un nuovo prezzo**, come mostrato nell'illustrazione seguente di esempio. Questa impostazione garantisce che i clienti possano inserire un prezzo quando esplorano il prodotto su una pagina PDP.

    ![Digitare il campo del prezzo in Commerce headquarters.](./media/KeyInPrice.png)
    
    L'illustrazione di esempio seguente mostra un elenco di varianti di prodotti di gift card digitali in Commerce headquarters, comprese due varianti di prezzo personalizzate.
    ![Esempio di varianti di prodotto di gift card digitali con variante di prezzo personalizzata](./media/DigitalGiftCards_ProductVariantsWithCustom.png)

- La modalità di consegna di una gift card digitale deve essere impostata su **Elettronico**. Nella pagina **Modalità di consegna** (**Retail e Commerce \> Impostazione canale \> Modalità di consegna**), seleziona la modalità di consegna **Elettronico** nel riquadro elenco, quindi aggiungi il prodotto della gift card digitale alla griglia nella scheda dettaglio **Prodotti** come mostrato nell'illustrazione seguente. Per ulteriori informazioni, vedi [Impostare modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Prodotti gift card digitali nella pagina Modalità di consegna in Commerce headquarters.](./media/ElectronicMode.PNG)
    
- Assicurati che un profilo di funzionalità online sia stato creato e associato al tuo punto vendita online in Commerce headquarters. Nel profilo di funzionalità, imposta l'opzione **Aggrega prodotti** su **Sì**. Questa impostazione garantisce l'aggregazione di tutti gli articoli tranne le gift card. Per ulteriori informazioni, vedi [Creare un profilo di funzionalità online](online-functionality-profile.md).
- Per assicurarti che i clienti ricevano un'e-mail dopo la fatturazione di una gift card, crea un nuovo tipo di notifica e-mail nella pagina **Profili di notifica e-mail** e imposta il campo **Tipo di notifica e-mail** su **Emetti gift card**. Per ulteriori informazioni, vedi [Impostare un profilo di notifica e-mail](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Aggiungere le immagini dei prodotti alla libreria multimediale di Creazione di siti di Commerce

È necessario aggiungere le immagini dei prodotti per le gift card digitali alla libreria multimediale di Creazione di siti di Commerce. Assicurati che i nomi dei file delle immagini delle gift card seguano le convenzioni di denominazione del tuo sito per le immagini dei prodotti. Per ulteriori informazioni, vedi [Caricare immagini](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Configurare un importo personalizzato per una gift card digitale in Creazione di siti di Commerce

Se una gift card digitale è configurata per consentire un importo personalizzato, questo comportamento deve essere abilitato anche [modulo buy box](add-buy-box.md) che viene utilizzato nelle PDP del tuo sito. Il modulo Buy box supporta la configurazione del modulo per consentire importi personalizzati. Puoi inoltre definire gli importi minimi e massimi consentiti per gli importi personalizzati.

Per configurare un importo personalizzato per una gift card digitale in Creazione di siti di Commerce, segui questi passaggi.

1. Vai al modulo Buy box utilizzato nelle PDP del tuo sito. Questo modulo Buy Box potrebbe essere implementato in un frammento, in un modello o in una pagina.
1. Seleziona **Modifica**.
1. Nel riquadro delle proprietà a destra, seleziona la casella di controllo **Consenti prezzo personalizzato**.
1. Facoltativo: per definire importi minimi e massimi per importi personalizzati, inserisci gli importi in **Prezzo minimo** e **Prezzo massimo**.
1. Seleziona **Fine modifica** e quindi seleziona **Pubblica**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo casella acquisti](add-buy-box.md)

[Modulo checkout](add-checkout-module.md)

[Modulo carrello](add-cart-module.md)

[Creare un nuovo prodotto in Commerce](create-new-product-commerce.md)

[Imposta la modalità di consegna](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Dimensioni prodotto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Impostare un profilo di notifica tramite posta elettronica](email-notification-profiles.md)

[Creare un profilo funzionalità online](online-functionality-profile.md)

[Supporto per gift card esterne](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
