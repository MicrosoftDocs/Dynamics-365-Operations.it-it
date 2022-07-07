---
title: Aggiungere un indirizzo a un ordine di servizio
description: In questo articolo viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015727"
---
# <a name="add-an-address-to-a-service-order"></a>Aggiungere un indirizzo a un ordine di servizio

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza. Quando si crea un ordine di assistenza, in esso vengono trasferite le informazioni relative all'indirizzo dal progetto a cui l'ordine di assistenza è collegato. È tuttavia possibile selezionare un'ubicazione alternativa dagli indirizzi già immessi in Microsoft Dynamics AX per i clienti, i fornitori, i siti, i magazzini, gli ordini di assistenza e i progetti.

È inoltre possibile creare un nuovo indirizzo. Per impostazione predefinita, il nuovo indirizzo viene trasferito al progetto. È tuttavia possibile specificare che il nuovo indirizzo è solo importante per questa istanza del servizio. In questo caso, il nuovo indirizzo non viene trasferito al progetto.

## <a name="create-a-customer-address-for-a-service-order"></a>Creare un indirizzo cliente per un ordine di assistenza.

Per aggiungere un indirizzo a un ordine di assistenza, effettuare le operazioni seguenti:

1. Vai a **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.

1. Aprire l'ordine di assistenza per cui si desidera creare un indirizzo.

1. Apri la scheda **Intestazione**.

1. Espandi la Scheda dettaglio **Indirizzo** e quindi seleziona **Aggiungi indirizzo** dalla barra degli strumenti della Scheda dettaglio.

1. Nella finestra di dialogo **Nuovo indirizzo**, immetti un nome univoco per l'indirizzo e completa i campi rimanenti. 

    > [!WARNING]
    > Se si immette lo stesso nome dell'indirizzo esistente, le informazioni immesse nei campi rimanenti sovrascriveranno le informazioni relative all'indirizzo esistente.

1. Seleziona **OK** per copiare il nuovo indirizzo nell'ordine di assistenza.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Specificare un indirizzo alternativo nell'ordine di assistenza

Per aggiungere un indirizzo alternativo a un ordine di assistenza, effettuare le operazioni seguenti:

1. Vai a **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.

1. Aprire l'ordine di assistenza per cui si desidera inserire un indirizzo alternativo.

1. Apri la scheda **Intestazione**.

1. Espandi la Scheda dettaglio **Indirizzo** e quindi seleziona **Altro indirizzo** dalla barra degli strumenti della Scheda dettaglio.

1. Nella finestra di dialogo **Selezione indirizzo** seleziona **Ordini di assistenza** dall'elenco a discesa sopra la griglia.

1. Seleziona un indirizzo, quindi fai clic su **OK** per copiarlo nell'ordine di assistenza.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]