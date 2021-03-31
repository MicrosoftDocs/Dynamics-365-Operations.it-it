---
title: Personalizzare la navigazione del sito
description: In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: cfd0a9559eb2b596adb822b228929e6855711bb4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222611"
---
# <a name="customize-site-navigation"></a>Personalizzare la navigazione del sito


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare una gerarchia di navigazione online personalizzate allo scopo di organizzare i prodotti per l'esplorazione nel sito di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In genere le vetrine online consentono ai clienti di individuare ed esplorare prodotti navigando tra le categorie di prodotti. Questa funzionalità è in genere fornita mediante delle schede nella parte superiore della pagina o una barra di navigazione a sinistra. In Dynamics 365 Commerce, è possibile creare e gestire la struttura gerarchica della navigazione nelle categorie e i prodotti inclusi nelle varie categorie.

## <a name="create-a-channel-navigation-hierarchy"></a>Creare una gerarchia di navigazione nei canali

Per creare una gerarchia di navigazione nei canali, effettuare le seguenti operazioni.

1. Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.
1. Selezionare **Gerarchie di categorie** e quindi **Nuova**.
1. Assegnare un nome alla gerarchia.

    > [!NOTE]
    > La categoria di primo livello creata è il nodo di categoria principale. Non verrà visualizzata nel sito. Per creare una gerarchia di categorie in cui un singolo nodo di primo livello è visualizzato nel sito, creare e denominare la categoria come figlio della categoria principale.

1. Selezionare **Nuovo nodo di categoria** e assegnare un nome alla categoria.
1. Continuare a creare categorie di pari livello e figlio come necessario.

Ora è possibile assegnare prodotti a ogni categoria creata sotto la categoria di primo livello.

## <a name="customize-the-order-of-categories"></a>Personalizzare l'ordine delle categorie

Per impostazione predefinita, le categorie definite verranno visualizzate in ordine alfabetico nel sito. Tuttavia, è anche possibile personalizzare l'ordine di visualizzazione delle categorie.

## <a name="assign-a-category-hierarchy-type"></a>Assegnare un tipo di gerarchia di categorie

1. Selezionare **Retail e Commerce \> Prodotti e categorie \> Gestione categorie e prodotti**.
1. Selezionare **Gerarchie di categorie**.
1. Nel riquadro azioni, nella scheda **Gerarchia di categorie**, nel gruppo **Imposta**, selezionare **Associa tipo gerarchia**.
1. Selezionare **Nuovo**.
1. Nel campo **Tipo di gerarchia di categorie**, selezionare **Gerarchia di navigazione nei canali**.
1. Nel campo **Gerarchia di categorie**, selezionare la gerarchia di navigazione nei canali creata in precedenza.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Pubblicare gerarchie di navigazione nuove o aggiornate

Per rendere disponibile la gerarchia di navigazione per la vetrina online, effettuare le seguenti operazioni.

1. Passare a **Retail e Commerce \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Nell'albero a sinistra, selezionare il punto vendita online.
1. Selezionare **Pubblica aggiornamenti canale**.
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Nell'elenco trovare e selezionare **Processo 1040**.
1. Selezionare **Esegui adesso**.
1. Ripetere i passaggi 5 e 6 per i processi 1070 e 1150.

## <a name="show-categories-on-your-site"></a>Visualizzare categorie nel sito

Per visualizzare la gerarchia di categorie nella vetrina online, è necessario aggiungere il modulo Menu di navigazione nella posizione appropriata in un modello o in un frammento. Il modulo Menu di navigazione visualizzerà quindi la gerarchia di navigazione, purché la gerarchia di navigazione sia stata pubblicata nel canale a cui il sito è associato.

> [!NOTE]
> Il modulo Menu di navigazione incluso nella libreria di modelli del punto vendita consente agli utenti di accedere solo alle categorie che non hanno sottocategorie. Per consentire ai clienti di accedere a categorie con sottocategorie, è necessario personalizzare il modulo Menu di navigazione.

## <a name="add-custom-navigation-options"></a>Aggiungere opzioni di navigazione personalizzate

Nel menu di navigazione, è possibile aggiungere opzioni di navigazione che non fanno parte della gerarchia di categorie di prodotti. Ad esempio, alla fine dell'elenco di categorie di prodotti, è possibile aggiungere un elemento **Contattaci** che punta a una pagina di contatto creata per il sito.

Per aggiungere opzioni di navigazione personalizzate al menu di navigazione, effettuare le seguenti operazioni.

1. Nel modello o nel frammento che si desidera personalizzare, selezionare il modulo Menu di navigazione.
1. Nel riquadro delle proprietà, nella scheda **Dati**, selezionare **Aggiungi elemento** per creare un nuovo elemento di navigazione CMS.
1. Immettere il testo del collegamento e un URL
1. Ripetere i passaggi 2 e 3 per aggiungere ulteriori opzioni di navigazione personalizzate.
1. Al termine, selezionare **Salva** per salvare il modello o il frammento, quindi selezionare **Fine modifica** per archiviarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Utilizzare i moduli](work-with-modules.md)

[Creare una pagina URL](create-page-url.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]