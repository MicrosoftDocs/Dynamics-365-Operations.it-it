---
title: Codici NMFC (National Motor Freight Classification)
description: Questo articolo descrive come lavorare con i codici NMFC (National Motor Freight Classification) in Microsoft Dynamics 365 Supply Chain Management
author: Weijiesa
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 522e4d4e26b04b5ca1dd317e433c5a20ff3cb12e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893267"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>Codici NMFC (National Motor Freight Classification)

[!include [banner](../includes/banner.md)]

I codici NMFC (National Motor Freight Classification) aiutano a classificare gli articoli che possono essere spediti. Il codice NMFC è una designazione utilizzata per raggruppare le merci. Consente alle aziende di trasporto di valutare le merci per la spedizione classificando gli articoli in base a considerazioni come capacità di entrare in un camion, problemi di carico, problemi di movimentazione e deperibilità. Le merci sono raggruppate in una di 18 classi di trasporto utilizzando una gamma di numeri da 50 a 500. La classe in cui è raggruppata una merce si basa su una valutazione di quattro caratteristiche di trasporto: densità, stivabilità, movimentazione e responsabilità. Insieme, queste caratteristiche stabiliscono la trasportabilità della merce.

Un codice NMFC è associato a ogni articolo di spedizione inferiore al carico camion (LTL). Ad esempio, a un laptop potrebbe essere assegnato un NMFC di classe 2.5, mentre ai cavi elettrici potrebbe essere assegnato un NMFC di classe 65.

Questa funzionalità può aiutare i lavoratori a utilizzare i codici NMFC per classificare gli articoli con spedizione LTL. Di seguito sono riportati alcuni esempi.

- Se la tua azienda include una descrizione del trasporto sulla polizza di carico (BOL), il vettore avrà un'idea di cosa sia il trasporto. Il trasporto è una classificazione importante perché molte società di trasporto basano il loro intero modello di business sui tipi di merci che spediscono.
- Questa classificazione potrebbe essere essenziale per la tua azienda perché viene utilizzata per determinare il costo di un determinato carico.
- La tua azienda può identificare la redditività di una società di logistica e trasporto LTL.

In questo articolo viene descritto come utilizzare i codici NMFC in Microsoft Dynamics 365 Supply Chain Management.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter creare codici NMFC, è necessario impostare tutte le classi di trasporto LTL che devono essere mappate ad essi. Le classi di trasporto LTL rappresentano categorie di articoli, mentre i codici NMFC sono correlati a merci specifiche in ciascuna delle 18 classi di trasporto. Per ulteriori informazioni su come lavorare con le classi LTL, vedere [Classi di carico inferiore a quello del camion (LTL)](ltl-class.md).

## <a name="create-an-nmfc-code"></a>Creare un codice NMFC

Per creare un codice NMFC, attenersi alla procedura seguente.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Codici NMFC**.
    - Andare a **Gestione trasporto \> Impostazioni \> Standard di trasporto \> Codici NMFC**.

1. Seleziona **Nuovo** per creare un codice NMFC. Quindi impostare i seguenti campi:

    - **Codice NMFC** – Immettere il codice NMFC per il tipo di merce.
    - **Nome**: immetti un nome per il codice NMFC.
    - **Classe LTL** - Seleziona la classe LTL associata al codice NMFC.
    - **Unità di movimentazione BOL** - Definire il tipo di movimentazione predefinito per la spedizione.

## <a name="example-set-up-nmfc-codes"></a>Esempio: Impostare i codici NMFC

L'esempio seguente mostra come impostare due diversi codici NMFC che possono essere utilizzati con prodotti diversi.

1. Vai a **Gestione magazzino \> Impostazioni \> Scorte \> Codici NMFC**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Codice NMFC:** *92.5*
    - **Nome:** *Computer*
    - **Classe LTL:** *92.5*
    - **Unità di movimentazione BOL:** *Unità*

1. Nel riquadro azioni selezionare **Salva**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella nuova riga, imposta i seguenti valori:

    - **Codice NMFC:** *125*
    - **Nome:** *Telefoni*
    - **Classe LTL:** *125*
    - **Unità di movimentazione BOL:** *Unità*

1. Nel riquadro azioni selezionare **Salva**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Classi di carico inferiore a quello del camion (LTL)](ltl-class.md)
- [Creare una polizza di carico](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
