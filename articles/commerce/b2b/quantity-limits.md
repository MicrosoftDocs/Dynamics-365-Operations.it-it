---
title: Impostare limiti di quantità di prodotti per i siti di e-commerce B2B
description: Questo articolo descrive come impostare i limiti di quantità dei prodotti per i siti di e-commerce business-to-business (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 76a7ad2c3095d1402ff214dbfee26b344b492681
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275679"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Impostare limiti di quantità di prodotti per i siti di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come impostare i limiti di quantità dei prodotti per i siti di e-commerce business-to-business (B2B).

La maggior parte dei prodotti ha un'unità di misura che ne definisce il raggruppamento. Il raggruppamento influisce sul modo in cui i prodotti possono essere venduti. Alcuni prodotti potrebbero avere un raggruppamento aggiuntivo per le quantità. Questo raggruppamento determina se i prodotti possono essere venduti come unità singole o multiple e se esiste un limite di quantità di ordine minimo o massimo che deve essere rispettato.

La funzione di limitazione della quantità garantisce che le quantità minime, massime, multiple e standard configurate in Microsoft Dynamics 365 Commerce (nelle impostazioni predefinite dell'ordine o nelle impostazioni del sito di Creazione di siti di Commerce) vengono applicate agli ordini dei clienti effettuati su un sito di e-commerce. I limiti di quantità di prodotto non sono attualmente supportati per il punto vendita (POS) e i servizi cliente.

Molti rivenditori offrono l'opzione degli ordini cliente, detti anche ordini speciali, per soddisfare vari requisiti di prodotti ed evasione. Di seguito sono riportati alcuni scenari comuni:

- Un cliente desidera che i prodotti con varianti specifiche vengano venduti in multipli di poche unità.
- Un cliente desidera prelevare i prodotti da un punto vendita o da una posizione diversa dal punto vendita o posizione in cui il cliente ha acquisito i prodotti. Tuttavia, gli standard di imballaggio per i punti vendita differiscono dagli standard di imballaggio per la distribuzione delle vendite online.
- Un cliente desidera acquistare un prodotto in edizione limitata con un limite di quantità massima per gli articoli che possono essere acquistati.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Attivare la funzionalità delle impostazioni predefinite dell'ordine in Commerce headquarters

Prima di poter impostare i limiti di quantità del prodotto, è necessario attivare la funzione delle impostazioni predefinite dell'ordine in Commerce headquarters.

Segui questi passaggi per attivare la funzionalità delle impostazioni predefinite dell'ordine.

1. Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Trova e seleziona la funzionalità **Supporta le impostazioni predefinite dell'ordine e del sito nell'ordine cliente**.
1. Nella parte inferiore del riquadro di destra, seleziona **Abilita ora**. 

## <a name="define-quantity-settings"></a>Definire le impostazioni di quantità 

È possibile definire le impostazioni di quantità nella pagina **Impostazioni ordine predefinite**.

Per definire le impostazioni di quantità segui questi passaggi. 

1. Vai a Prodotto **Retail e Commerce \> Prodotti e categorie \> Prodotti rilasciati per categorie**.
1. Seleziona un prodotto rilasciato.
1. Nella scheda **Gestione articoli** del riquadro azioni, nel gruppo **Impostazioni ordine**, seleziona **Impostazioni ordine predefinite**. 
1. Nella pagina **Impostazioni ordine predefinite** nella scheda dettaglio **Ordine cliente** nella sezione **Quantità di vendita** imposta le quantità di vendita del prodotto:

    - **Multiplo** - La quantità che il prodotto può essere acquistato in multipli.
    - **Quantità ordine minima** - Il numero minimo di prodotti che devono essere acquistati.
    - **Quantità ordine massima** - Il numero massimo di prodotti che possono essere acquistati.
    - **Quantità ordine standard** - La quantità predefinita che viene inserita automaticamente quando il prodotto viene selezionato.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Attivare la funzione dei limiti di quantità degli ordini B2B in Creazione di siti di Commerce

Per attivare la funzione dei limiti di quantità degli ordini B2B in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **Impostazioni sito \> Estensioni**
1. Sotto **Abilita limiti quantità ordine**, seleziona **Abilitato per clienti B2B** nel menu a discesa. 

> [!NOTE] 
> Le impostazioni aggiornati del generatore di siti avranno effetto solo dopo l'aggiornamento del file app.settings.json. Per ulteriori informazioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare un sito di e-commerce B2B](set-up-b2b-site.md)

[Gestire partner commerciali B2B utilizzando gerarchie di clienti](partners-customer-hierarchies.md)

[Gestione degli utenti partner commerciali sui siti di e-commerce B2B](manage-b2b-users.md)

[Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
