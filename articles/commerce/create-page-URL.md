---
title: Creare un URL di pagina
description: In questo argomento vengono descritti le procedure e i concetti di base per la creazione di un URL di pagina nel sito.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8e221bd975fd984379724b751f6c026acfda7b07
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207897"
---
# <a name="create-a-page-url"></a>Creare un URL di pagina


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti le procedure e i concetti di base per la creazione di un URL di pagina nel sito.

## <a name="overview"></a>Panoramica

L'URL completo, o assoluto, che punta a una pagina nel sito è costituito da più parti distinte. Ad esempio, l'URL `https://www.contoso.com/en-us/contactus` include le seguenti parti:

- `https://www.contoso.com` – Il protocollo HTTP e il dominio del sito.
- `/en-us` – Il percorso della lingua del sito.
- `/contactus` – L'URL relativo della pagina **Contattaci**. Un URL relativo è anche denominato *slug* URL.

L'utente stabilisce il dominio del sito e il percorso della lingua facoltativo del sito durante la configurazione del sito. È possibile aggiungere più domini e percorsi di lingua al sito mediante la pagina dei punti vendita online nelle impostazioni del sito.

Lo slug URL di una pagina esiste come entità autonoma nell'ambiente di creazione di siti. Un URL di pagina è composto da due parti: un nome che rappresenta lo slug URL e un puntatore a una pagina nel proprio sito o in un sito esterno. Un URL di pagina può anche essere configurato per fungere da reindirizzamento a un'altra pagina nel proprio sito o in un sito esterno.

## <a name="create-a-page-url"></a>Creare un URL di pagina

È possibile creare URL di pagina in due modi:

- Automaticamente, quando si crea una pagina.
- Manualmente, dalla pagina **URL**.

### <a name="create-a-page-url-when-you-create-a-page"></a>Creare un URL di pagina quando si crea una pagina

Se si immette un nome nel campo **URL** quando si crea una nuova pagina, un URL di pagina che punta a quella pagina viene creato automaticamente nella pagina **URL**. Dopo aver pubblicato l'URL e la pagina a cui punta, gli utenti del sito (i clienti) possono accedere alla pagina associata all'URL.

> [!NOTE]
> Se si pubblica un URL senza pubblicare la pagina a cui punta, gli utenti del sito vedono un errore 404 quando tentano di accedere alla pagina. Se si pubblica una pagina senza pubblicare l'URL che punta alla stessa, la pagina non è accessibile con un URL.

### <a name="manually-create-a-page-url"></a>Creare manualmente un URL di pagina

Quando si creano nuove pagine, non è necessario specificare un URL di pagina. Se si lascia vuoto il campo URL, la pagina viene creata in uno stato non collegato. In questo caso, i clienti non potranno accedere alla pagina, anche se è stata pubblicata. Per rendere la pagina accessibile, è necessario creare manualmente l'URL e collegarlo alla pagina.

Per creare manualmente l'URL per una pagina, effettuare le seguenti operazioni.

1. Nella pagina **URL**, selezionare **Nuovo**.
1. Selezionare la pagina del sito da associare all'URL.
1. Immettere lo slug URL e selezionare **OK**.

A questo punto, l'URL è in stato bozza. Deve essere pubblicato affinché gli utenti del sito possano accedere alla pagina associata.

## <a name="update-a-page-url"></a>Aggiornare un URL di pagina

Per aggiornare la pagina di destinazione di un URL di pagina, effettuare le seguenti operazioni.

1. Nella pagina **URL**, selezionare l'URL da aggiornare.
1. Nel riquadro delle proprietà a destra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al campo della pagina di destinazione.
1. Nella finestra di dialogo, selezionare un'altra pagina e quindi **OK**.
1. Salvare e pubblicare l'URL.

## <a name="redirect-a-page-url"></a>Reindirizzare un URL di pagina

In alcuni casi, è possibile che si voglia visualizzare una pagina diversa quando i clienti richiedono un URL specifico. In tali casi, l'approccio migliore e più semplice consiste in genere nel modificare la pagina a cui l'URL di pagina punta. Tuttavia, si potrebbero avere motivi legittimi di utilizzare reindirizzamenti HTTP 301 o 3023 per reindirizzare le richieste di un URL a un URL differente.

Per reindirizzare un URL a un URL differente, effettuare le seguenti operazioni.

1. Nella pagina **URL**, selezionare l'URL da aggiornare.
1. Nel riquadro delle proprietà a destra, selezionare **Reindirizza**.
1. Selezionare una destinazione per il reindirizzamento.

    - Per puntare a un'altra pagina nel sito, selezionare **URL interno**, selezionare il pulsante con i puntini di sospensione (**...**) e quindi selezionare l'URL a cui reindirizzare.
    - Per puntare a una pagina in un sito esterno, selezionare **URL esterno**, quindi immettere l'URL completo di quella pagina. Assicurarsi di includere il protocollo. Ad esempio, immettere `https://domain.com/new/page`. Se l'URL reindirizza già a un URL interno, è necessario selezionare **Cancella selezione** prima di poter immettere un URL esterno.

1. Selezionare un tipo di reindirizzamento:

    - **Reindirizzamento permanente (301)** - Selezionare questa opzione quando si sa che il contenuto viene spostato in permanenza e che l'URL precedente non verrà ripristinato. I motori di ricerca assegneranno il valore di ottimizzazione del motore di ricerca dell'URL di reindirizzamento all'URL a cui si è reindirizzati e aggiorneranno il relativo record per visualizzare il nuovo URL. 
    - **Reindirizzamento temporaneo (302)** - Selezionare questa opzione per reindirizzare il traffico senza aggiornare i motori di ricerca. Questo approccio è in genere utilizzato se il contenuto viene ripristinato rapidamente al relativo URL precedente.

1. Quando si è pronti per implementare il reindirizzamento, salvare e pubblicare l'URL.

## <a name="additional-resources"></a>Risorse aggiuntive

[Personalizzare la navigazione del sito](customize-site-navigation.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Aggiungere lingue al sito](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]