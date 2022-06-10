---
title: Modulo Condivisione social
description: In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d145602a217b32b97142251c65d51945569be9ac
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780895"
---
# <a name="social-share-module"></a>Modulo di condivisione social

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli condivisione social e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli di condivisione social consentono agli utenti di condividere gli URL delle pagine del sito di e-commerce sui social media come Facebook, Twitter, Pinterest e LinkedIn. Gli URL delle pagine del sito possono essere condivisi anche tramite posta elettronica. I moduli di condivisione social sono comunemente utilizzati nelle pagine dei dettagli del prodotto (PDP) per aiutare gli utenti a condividere le informazioni sui prodotti.

Ogni modulo di condivisione social è un contenitore per moduli di articoli di condivisione social. Ogni modulo di articolo di condivisione social può essere configurato per puntare a un sito di social media specifico. Integrazione con Facebook, Twitter, Pinterest, LinkedIn e la posta elettronica sono supportati per impostazione predefinita. Quando un utente del sito seleziona un simbolo di social media, viene avviato un iframe HTML per il rispettivo sito di social media. All'interno dell'iframe, l'utente può accedere e pubblicare il contenuto della pagina che stava visualizzando.

Ogni piattaforma di social media può tenere traccia dei cookie, quindi questo modulo richiede agli utenti del sito di accettare il messaggio di notifica del consenso ai cookie. Quando il consenso ai cookie non viene accettato, il modulo verrà nascosto nella pagina. Per ulteriori informazioni vedere [Conformità dei cookie](cookie-compliance.md).

La seguente illustrazione evidenzia un esempio di un modulo di condivisione social utilizzato in una pagina dei dettagli del prodotto.

![Esempio di modulo di condivisione social.](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Proprietà del modulo di condivisione social

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| Titolo                  | Testo | Questa proprietà specifica una didascalia per il modulo. |
| Orientamento | **Verticale** o **Orizzontale**  | Questa proprietà definisce l'orientamento del layout per gli elementi dei social media. |

## <a name="social-share-item-module-properties"></a>Proprietà del modulo articoli di condivisione social
| Nome proprietà             | Valore                 | Descrizione |
|---------------------------|-----------------------|-------------|
| Social media              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail** | Un menu a discesa con un elenco di piattaforme di social media. |
| Icona |Immagine    | Questa sarà l'immagine che verrà mostrata per i rispettivi social media. Come procedura consigliata, fare riferimento all'SDK della piattaforma di social media per l'immagine consigliata da utilizzare per ciascuna piattaforma. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Aggiungere un modulo di condivisione social al modulo casella acquisti

Per aggiungere un modulo di condivisione social al modulo casella acquisti, seguire questi passaggi.

1. Nel sito Fabrikam selezionare **Pagine**, quindi selezionare la pagina **DefaultPDP** per aprire la pagina dei dettagli del prodotto. 
1. Nello slot **Buybox (richiesto)** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Condivisione social** e quindi seleziona **OK**.
1. Nello slot **Condivisione social** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **SocialShare** e quindi seleziona **OK**.
1. Nel riquadro delle proprietà del modulo **SocialShare**, sotto **Orientamento**, selezionare **Orizzontale**. Aggiungere una didascalia secondo necessità.
1. Nello slot **SocialShare** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **SocialShareItem** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Social media**, selezionare **Facebook**.
1. Nel riquadro delle proprietà del modulo **SocialShareItem** sotto **Icona**, selezionare **+ Aggiungi immagine**.
1. Nella finestra di dialogo **Selettore multimediale** selezionare l'immagine del logo Facebook e quindi **OK**. Se nessuna immagine del logo Facebook è presente, selezionare **Carica un nuovo elemento multimediale** per caricarne una.
1. Aggiungere e configurare altri moduli **SocialShareItem** secondo necessità.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. La pagina mostrerà il modulo di condivisione social.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo casella acquisti](add-buy-box.md)

[Conformità dei cookie](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
