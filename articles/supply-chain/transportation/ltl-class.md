---
title: Classi di carico inferiore a quello del camion (LTL)
description: Questo articolo spiega cosa sono le classi di carico inferiori a quello del camion (LTL) e descrive come configurarle in Microsoft Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9c1c7233b637b84ec901d7f83ae00f8a04895edb
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838420"
---
# <a name="less-than-truckload-ltl-classes"></a>Classi di carico inferiore a quello del camion (LTL)

[!include [banner](../includes/banner.md)]

Una classe LTL è una classe di spedizione merci utilizzata per classificare gli articoli che possono essere spediti. In generale, ogni tipo di prodotto o merce ha un codice NMFC (National Motor Freight Classification) che corrisponde a un numero di classe di trasporto specifico per le spedizioni LTL. Le classi di trasporto LTL rappresentano categorie di articoli, mentre i codici NMFC sono correlati a merci specifiche in ciascuna delle 18 classi di trasporto.

Questa funzionalità consente di usare il sistema per svolgere le attività seguenti:

- Definire le classi di trasporto LTL utilizzate nella tua azienda.
- Assegnare ogni classe LTL a un codice NMFC nella pagina **Codici NMFC**. Per ulteriori informazioni, vedere [Codici NMFC (National Motor Freight Classification)](nmfc-codes.md).
- Assegna un codice NMFC (e quindi il codice LTL associato) a ciascun prodotto nella pagina **Prodotti**.
- Valutare accuratamente la classe LTL di ciascun prodotto a cui è assegnato un codice NMFC.
- Determinare i requisiti di imballaggio per ciascuna classe LTL controllando gli standard internazionali LTL. In questo modo, ti assicuri che i tuoi prodotti saranno ben protetti e spediti in sicurezza.
- Ottieni stime di spedizione accurate, in base alla classe di trasporto LTL per ogni prodotto.

In questo articolo viene descritto come creare classi LTL in Microsoft Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>Creare una classe LTL

Per creare una classe LTL, attenersi alla procedura seguente.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Classi LTL**.
    - Andare a **Gestione trasporto \> Impostazioni \> Standard di trasporto \> Classi LTL**.

2. Nel riquadro azioni seleziona **Nuovo** per creare una classe LTL. Quindi impostare i seguenti campi:

    - **Classe LTL** - Immettere l'identificatore (ID) della classe LTL interna della propria azienda per il tipo di merce. La maggior parte delle aziende utilizza lo standard internazionale. In tal caso, il valore di questo campo corrisponderà al valore del campo **Classe**. Tuttavia, se la tua azienda utilizza il proprio standard, inserisci un codice conforme a quello standard.
    - **Nome** - Immettere un nome descrittivo che aiuterà te e gli altri utenti a selezionare la classe LTL corretta per ogni codice NMFC.
    - **Classe** - Immettere l'ID classe LTL standard internazionale per il tipo di merce. Il codice che inserisci qui deve essere conforme allo standard ufficiale.

## <a name="example-set-up-ltl-classes"></a>Esempio: Impostare le classi LTL

L'esempio seguente mostra come impostare due diversi classi LTL che possono essere utilizzati con tipi di prodotti diversi.

1. Vai a **Gestione magazzino \> Impostazione \> Inventario \> Classi LTL** o **Gestione trasporto \> Impostazione \> Standard di trasporto \> Classi LTL**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Classe LTL:** *92.5*
    - **Nome:** *Computer, monitor, frigoriferi*
    - **Classe:** *92.5*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Classe LTL:** *125*
    - **Nome:** *Piccoli elettrodomestici*
    - **Classe:** *125*

1. Nel riquadro azioni selezionare **Salva**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Codici NMFC (National Motor Freight Classification)](nmfc-codes.md)
- [Creare una polizza di carico](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
