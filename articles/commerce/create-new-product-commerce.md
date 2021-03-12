---
title: Creare un nuovo prodotto in Commerce
description: In questo argomento viene descritto come creare un nuovo prodotto in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3b578c1bdfe1c6b4bf66cc85cc09ed906fb812a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965316"
---
# <a name="create-a-new-product-in-commerce"></a>Creare un nuovo prodotto in Commerce


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un nuovo prodotto in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Un prodotto viene principalmente definito da un numero prodotto, un nome e una descrizione. Tuttavia, anche altri dati sono necessari per descrivere un prodotto o servizio:

## <a name="create-a-new-product"></a>Creare un nuovo prodotto

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Prodotti per categoria**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'elenco a discesa **Tipo prodotto**, selezionare **Articolo** o **Servizio**.
1. Nell'elenco a discesa **Sottotipo di prodotto**, selezionare **Prodotto** (se il prodotto non avrà varianti) o **Rappresentazione generale prodotto** (se il prodotto avrà varianti).
1. Nella casella **Numero prodotto**, immettere un numero di prodotto se non è già prepopolato.
1. Nella casella **Nome prodotto** immettere un nome di prodotto.
1. Nella casella **Nome di ricerca** immettere un nome di ricerca.
1. Nell'elenco a discesa **Categoria di vendite al dettaglio**, selezionare una categoria appropriata.
1. Se il prodotto è un kit, selezionare **Sì** per **Kit di prodotto**.
1. Se il sottotipo di prodotto è rappresentazione generale prodotto, impostare **Gruppo di dimensioni prodotto** per includere le varianti supportate. Le opzioni includono **Colore**, **Dimensione**, **Stile** e **Configurazione**. Potrebbe essere necessario creare ulteriori gruppi di dimensioni prodotto, se necessario.
1. Nell'elenco a discesa **Tecnologia di configurazione**, selezionare un'opzione appropriata.
1. Selezionare **OK**.

L'immagine seguente mostra un esempio di prodotto aggiunto.

![Creare un prodotto](media/create-new-product.png)

Una volta aggiunto un prodotto, è possibile impostare ulteriori dati per lo stesso, ad esempio **Descrizione prodotto**, **Gruppi di varianti**, **Gruppi di dimensioni**, **Attributi del prodotto** e **Prodotti correlati**.

L'immagine seguente mostra dettagli aggiuntivi di un prodotto.

![Dettagli prodotto](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Crea varianti prodotto

Se il sottotipo di prodotto è **Rappresentazione generale prodotto**, dovranno essere create varianti specifiche. 

Per creare delle varianti, completare i passaggi seguenti.

1. Nel riquadro azioni selezionare **Varianti prodotto**.
1. Se sono stati selezionati gruppi di varianti nel riquadro azioni, selezionare **Suggerimenti varianti*.
1. Selezionare le varianti che si desidera supportare per il prodotto.
1. Selezionare **Crea**.

## <a name="release-a-product"></a>Rilasciare un prodotto

Per vendere un prodotto, deve essere prima rilasciato a una persona giuridica.

1. Dalla pagina del prodotto, selezionare **Rilascia prodotti**.

    ![Rilasciare un prodotto](media/create-new-product-3.png)

1. Selezionare il prodotto da rilasciare, quindi selezionare **Avanti**.

    ![Scegliere il prodotto da rilasciare](media/create-new-product-4.png)

1. Selezionare il set di varianti di prodotto da rilasciare, quindi selezionare **Avanti**.

    ![Scegliere le varianti da rilasciare](media/create-new-product-5.png)

1. Selezionare la persona giuridica, quindi **Avanti**.

    ![Scegli persona giuridica](media/create-new-product-6.png)

1. Selezionare **Fine**.

    ![Terminare il rilascio del prodotto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Configurare un prodotto rilasciato

Una volta rilasciato il prodotto, sarà necessario eseguire un'ulteriore configurazione che include l'aggiunta di un prezzo al prodotto.

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Prodotti rilasciati per categoria**.
1. Selezionare il nodo della categoria di prodotto per il prodotto che è stato rilasciato, quindi selezionare il prodotto dall'elenco dei prodotti.
1. Nel riquadro azioni selezionare **Modifica**.
1. Nella sezione **Acquisti**, configurare tutte le proprietà richieste tra cui **Unità**, **Prezzo** e **Quantità**.
1. Nel riquadro azioni, selezionare **Convalida** per assicurarsi che non vengano segnalati errori per i campi mancanti.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente illustra un esempio di configurazione per un prodotto rilasciato.

![Configurare un prodotto rilasciato](media/create-new-product-8.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare persone giuridiche](channels-legal-entities.md)

[Creare un gruppo di varianti](create-variant-group.md) 
