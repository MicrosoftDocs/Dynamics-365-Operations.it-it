---
title: Abilitare suggerimenti personalizzati sui prodotti
description: Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9b847a67306861052a360e0137e2e257b056888e
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154274"
---
# <a name="enable-personalized-recommendations"></a>Abilitare suggerimenti personalizzati

[!include [banner](includes/banner.md)]

Questo argomento descrive come rendere disponibili suggerimenti personalizzati sui prodotti per i clienti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce, i rivenditori possono rendere disponibili suggerimenti personalizzati sui prodotti (noti anche come personalizzazione). In questo modo, i suggerimenti personalizzati possono essere incorporati nell'esperienza cliente online e nel POS. Quando la funzionalità di personalizzazione è attivata, il sistema può associare l'acquisto di un utente e le informazioni sul prodotto per generare suggerimenti personalizzati sul prodotto.

## <a name="personalization-prerequisites"></a>Prerequisiti per la personalizzazione

Prima di rendere disponibili i suggerimenti consigli sui prodotti per i clienti, tenere presente che i suggerimenti sui prodotti sono supportati solo per gli utenti di Commerce che hanno migrato il loro archivio a quello di Azure Data Lake. Prima che i clienti possano ricevere suggerimenti personalizzati sui prodotti, i rivenditori devono [attivare i suggerimenti sui prodotti](enable-product-recommendations.md).

> [!NOTE]
> Attivando i suggerimenti sui prodotti, si attiva anche la personalizzazione. Tuttavia, se si disattiva la personalizzazione, non si disattivano gli altri tipi di suggerimenti sui prodotti.

Per ulteriori informazioni relative ai suggerimenti sui prodotti, vedere [Panoramica suggerimenti sul prodotto](product-recommendations.md).

## <a name="turn-on-personalization"></a>Attivare la personalizzazione

Per attivare la personalizzazione, effettuare le seguenti operazioni.

1. Andare a **Retail e Commerce \> Suggerimenti sul prodotto \> Parametri suggerimenti**.
1. Nell'elenco Parametri condivisi di vendita al dettaglio, selezionare **Elenchi di suggerimenti**.
1. Impostare l'opzione **Abilita personalizzazione** su **Sì**.

![Attivare la personalizzazione](./media/enablepersonalization.png)

> [!NOTE]
> Quando si attiva la personalizzazione, viene avviato il processo di generazione di elenchi di suggerimento personalizzati sui prodotti. Potrebbe essere necessario fino a un giorno prima che questi elenchi siano disponibili e visibili online nel POS.

## <a name="personalized-lists"></a>Elenchi personalizzati

Oltre a consentire la personalizzazione degli elenchi generati automaticamente dal computer, il servizio di suggerimenti consente la personalizzazione dell'esperienza di individuazione dei prodotti sia online che nel POS.

Una volta attivata la personalizzazione, i rivenditori possono mostrare agli acquirenti elenchi personalizzati "Selezioni personalizzate" online o elenchi "Prodotti consigliati" nei terminali POS. Inoltre, i rivenditori possono applicare la personalizzazione agli elenchi di suggerimenti sui prodotti esistenti e fornire la possibilità di rifiutare esplicitamente il Regolamento generale sulla protezione dei dati (GDPR) per gli utenti autenticati. Se si disattiva la personalizzazione, si disattivano anche queste funzionalità.

### <a name="online-picks-for-you-lists"></a>Elenchi "Selezioni personalizzate" online

Un elenco "Selezioni personalizzate" è un elenco AI-ML (intelligenza artificiale-machine learning) che mostra a un utente autenticato un elenco personalizzato di prodotti suggeriti. Questo elenco si basa sullo storico degli acquisti omnicanale dell'utente. I suggerimenti personalizzati vengono aggiornati dinamicamente man mano che l'utente effettua più acquisti. Questo tipo di elenco supporta il filtro delle categorie, di modo che i rivenditori possano mostrare le selezioni più appropriate, in base alle gerarchie di navigazione.

Affinché l'elenco "Selezioni personalizzate" sia visualizzato su qualsiasi pagina di e-Commerce, devono essere soddisfatti i seguenti requisiti utente:

- Gli utenti devono aver effettuato l'accesso. Gli utenti anonimi non vedranno i suggerimenti personalizzati.
- Gli utenti devono avere almeno un acquisto nel proprio account.
- Gli utenti devono acconsentire esplicitamente a ricevere suggerimenti personalizzati.

La seguente illustrazione mostra un esempio di elenco "Selezioni personalizzate" in una pagina del punto vendita online.

![Elenco Selezioni personalizzate online](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>Elenchi "Prodotti consigliati" nel POS

Per migliorare l'esperienza di fidelizzazione dei clienti, i rivenditori possono personalizzare le pagine dei dettagli dei clienti esistenti aggiungendo un elenco contestuale "Prodotti consigliati".

La seguente illustrazione mostra un esempio di elenco "Prodotti consigliati" in un terminale POS.

![Elenco "Prodotti consigliati" nel POS](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Applicare la personalizzazione a elenchi di suggerimenti esistenti

I rivenditori possono applicare la personalizzazione a elenchi di suggerimenti esistenti, come "Novità", "Di tendenza", "Più venduti", "Alle persone piace anche" e "Spesso acquistati insieme". Quando la personalizzazione viene applicata a elenchi esistenti, gli articoli che un utente connesso ha acquistato in precedenza vengono rimossi da tali elenchi. Per gli utenti anonimi e quelli che hanno rinunciato a ricevere suggerimenti personalizzati, vengono visualizzate le versioni predefinite degli elenchi esistenti. Pertanto, i rivenditori non devono gestire manualmente esperienze di pagina distinte.

Ad esempio, un utente che ha effettuato l'accesso ha già acquistato l'orologio nero e gli stivali da lavoro marroni che compaiono nell'elenco "Di tendenza - Predefinito" nella figura seguente. Pertanto, l'utente vedrà dei nuovi prodotti anziché tali prodotti, come mostrato nell'elenco "Di tendenza - Personalizzato".

![Applicare la personalizzazione](./media/applypersonalization.png)

Per applicare la personalizzazione a un elenco di suggerimenti esistente in Creazione di siti di Commerce, attenersi alla seguente procedura.

1. Aprire una pagina di Creazione di siti Web che contiene un modulo Raccolta prodotti.
1. Selezionare il modulo Raccolta prodotti nel pannello di navigazione a sinistra.
1. Selezionare l'elenco sotto **Prodotti** nel pannello di navigazione a destra.
1. Nella finestra di dialogo **Seleziona configurazione elenco di prodotti**, sotto **Tipo**, selezionare il tipo di elenco.
1. Selezionare la casella di controllo **Applica personalizzazione**, quindi selezionare **OK**.

    ![Applicare la personalizzazione a un elenco Di tendenza](./media/ApplyPersonalizationToTrending.PNG)

1. Salvare la pagina, finalizzare la modifica e pubblicarla. Dopo la pubblicazione della pagina, gli utenti che hanno effettuato l'accesso vedranno elenchi Di tendenza personalizzati.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare ADLS in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilita suggerimenti sul prodotto](enable-product-recommendations.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Aggiungere suggerimenti sul prodotto su POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)
