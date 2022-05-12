---
title: Impatto sull'estendibilità dei cataloghi di Commerce per le personalizzazioni B2B
description: Questo argomento descrive l'impatto sull'estendibilità della funzionalità Cataloghi di Commerce per B2B in Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: aff333bfe8003233dd5d8181aa8c5dd7eaeffcd0
ms.sourcegitcommit: 0abc777986112ea2332f5bf0e815b303b952356c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "8656850"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Impatto sull'estendibilità dei cataloghi di Commerce per le personalizzazioni B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo argomento descrive l'impatto sull'estendibilità della la funzionalità **Cataloghi di Commerce per B2B** in Microsoft Dynamics 365 Commerce.

Se sei interessato ad estendere il contesto del catalogo a scenari personalizzati, le tue personalizzazioni potrebbero dover essere aggiornate. Questo aggiornamento segue la procedura standard che i clienti devono seguire, poiché le loro personalizzazioni potrebbero non supportare automaticamente le funzionalità più recenti dopo che gli aggiornamenti sono stati eseguiti. Se le tue personalizzazioni includono nuove funzionalità o correzioni di bug nelle loro esperienze, ti consigliamo di aggiornare il codice di personalizzazione di conseguenza. Questo aggiornamento assomiglia alle modifiche che Microsoft potrebbe aver apportato al codice principale.

Esamina i casi di personalizzazione che seguono per determinare se le tue personalizzazioni devono essere aggiornate.

> [!NOTE]
> - Tutte le API (Application Programming Interface) di merchandising devono essere compatibili con il catalogo. Pertanto, è fondamentale che tu passi il parametro **CatalogID**.
> - Il catalogo predefinito (**CatalogID**=**0**) non è un catalogo valido per gli utenti business-to-business (B2B) collegati. Pertanto, tutte le chiamate API che passano "0" o utilizzano un valore predefinito avranno esito negativo, poiché gli utenti del sito non hanno accesso al catalogo 0. Per ottenere l'esperienza corretta, le chiamate API del cliente devono essere aggiornate in modo che trasmettano l'ID catalogo selezionato nel selettore catalogo. Se utilizzi un valore predefinito e l'utente cambia catalogo, il sito Web deve fornire i dati per il catalogo selezionato. Pertanto, per abbinare le API eseguite dal codice principale di Commerce, le API personalizzate devono passare il catalogo selezionato.

I seguenti casi di personalizzazione richiedono gli aggiornamenti di sviluppo:

- **Caso 1:** Un cliente presenta la propria [azione dati](e-commerce-extensibility/data-actions.md) che chiama un'API o un'azione dati relativa al prodotto. Sono necessari i seguenti passaggi di aggiornamento:

    1. Se l'azione dati utilizza una chiamata API diretta, aggiorna l'azione dati in modo che trasmetta l'ID catalogo, come mostrato nell'illustrazione di esempio seguente.

        ![Azione dati aggiornata che trasmette l'ID catalogo.](./media/customization1_a.png)

    1. Se l'azione dati richiama un'azione dati relativa al prodotto diversa all'interno della personalizzazione, il codice deve essere aggiornato in modo che passi alcuni nuovi parametri, ad esempio **requestContext**. Il parametro **requestContext** viene utilizzato per recuperare l'ID catalogo corrente, come mostrato nell'illustrazione di esempio seguente.

        ![Azione dati aggiornata che trasmette il nuovo parametro.](./media/customization1_b.png)

- **Caso 2:** Un cliente ha un'[azione dati sostituita](e-commerce-extensibility/data-action-overrides.md). È necessario il seguente passaggio di aggiornamento:

    - Aggiorna l'azione dati come per il caso 1.

- **Caso 3:** Un cliente ha un'estensione di visualizzazione, un modulo iniettore di script o un [modulo clonato](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) che include chiamate ad API o azioni dati. È necessario il seguente passaggio di aggiornamento:

    - Aggiorna il codice come per il caso 1, come mostrato nell'illustrazione di esempio seguente.

       ![Codice aggiornato che trasmette il nuovo parametro.](./media/customization3.png)

- **Caso 4:** Un cliente usa una chiamata API **getById**. È necessario il seguente passaggio di aggiornamento:

    - Passa alla chiamata API **getByIds** perché la chiamata API **getById** presenta alcune limitazioni e non supporta il riconoscimento del catalogo.

- **Caso 5:** Un cliente dispone di un'azione dati che recupera informazioni per più prodotti che possono provenire da cataloghi diversi. È necessario il seguente passaggio di aggiornamento:

    - Dividi le chiamate API per ID catalogo. Ad esempio, per le API del carrello, il carrello può contenere prodotti di cataloghi diversi. Le righe di prodotto devono essere raggruppate per ID catalogo e devono chiamare l'API per ciascun catalogo separatamente, come mostrato nell'illustrazione di esempio seguente.

        ![Azione dati aggiornata che raggruppa le righe di prodotto per ID catalogo.](./media/customization5.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Crea cataloghi di Commerce per siti B2B](catalogs-b2b-sites.md)

[Domande frequenti sui cataloghi di Commerce per B2B](catalogs-b2b-sites-FAQ.md)
