---
title: Aggiungere un indirizzo a un ordine di servizio
description: In questo argomento viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c8f00eb1a1fe2ef3aea22da20ce218d7568f64
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966057"
---
# <a name="add-an-address-to-a-service-order"></a>Aggiungere un indirizzo a un ordine di servizio    

[!include [banner](../includes/banner.md)]


In questo argomento viene descritto come aggiungere un indirizzo cliente a un ordine di assistenza. Quando si crea un ordine di assistenza, in esso vengono trasferite le informazioni relative all'indirizzo dal progetto a cui l'ordine di assistenza è collegato. È tuttavia possibile selezionare un'ubicazione alternativa dagli indirizzi già immessi in Microsoft Dynamics AX per i clienti, i fornitori, i siti, i magazzini, gli ordini di assistenza e i progetti.

È inoltre possibile creare un nuovo indirizzo. Per impostazione predefinita, il nuovo indirizzo viene trasferito al progetto. È tuttavia possibile specificare che il nuovo indirizzo è solo importante per questa istanza del servizio. In questo caso, il nuovo indirizzo non viene trasferito al progetto.

## <a name="create-a-customer-address-for-a-service-order"></a>Creare un indirizzo cliente per un ordine di assistenza.

Per aggiungere un indirizzo a un ordine di assistenza, effettuare le operazioni seguenti:

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Aprire l'ordine di assistenza per cui si desidera creare un indirizzo.

3.  Nel **riquadro azioni** fare clic su **Modifica**, quindi fare clic su **Visualizzazione intestazione**.

4.  Nella Scheda dettaglio **Indirizzo** fare clic su **Aggiungi indirizzo**.

5.  Nel modulo **Nuovo indirizzo**, immettere un nome univoco per l'indirizzo e completare i campi rimanenti. 
    

    > [!WARNING]
    > <P>Se si immette lo stesso nome dell'indirizzo esistente, le informazioni immesse nei campi rimanenti sovrascriveranno le informazioni relative all'indirizzo esistente.</P>


6.  Fare clic su **OK** per copiare il nuovo indirizzo nell'ordine di assistenza.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Specificare un indirizzo alternativo nell'ordine di assistenza

Per aggiungere un indirizzo alternativo a un ordine di assistenza, effettuare le operazioni seguenti:

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Aprire l'ordine di assistenza per cui si desidera inserire un indirizzo alternativo.

3.  Nel **riquadro azioni** fare clic su **Modifica**, quindi fare clic su **Visualizzazione intestazione**.

4.  Nella Scheda dettaglio **Indirizzo** fare clic su **Altro indirizzo**.

5.  Nel modulo **Selezione indirizzo**, nel campo **Tipo di record**, selezionare **Ordini di assistenza**.

6.  Selezionare un indirizzo, quindi fare clic su **OK** per copiarlo nell'ordine di assistenza.


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]