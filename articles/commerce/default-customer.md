---
title: Creare un cliente predefinito
description: Questo articolo descrive come creare un cliente predefinito da utilizzare durante la creazione di un canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 79e145c21be9178622b7c105afefecb78062e3b5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273587"
---
# <a name="create-a-default-customer"></a>Creare un cliente predefinito

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare un cliente predefinito da utilizzare durante la creazione di un canale in Microsoft Dynamics 365 Commerce.

Quando si crea un canale, sarà necessario fornire un cliente predefinito. Un cliente predefinito può essere creato facilmente dopo aver creato il gruppo di clienti e la rubrica clienti.

## <a name="create-a-customer-group"></a>Creare un gruppo di clienti

Se non esistono ancora gruppi di clienti, è possibile crearne uno. Esempi possono essere gruppi per rappresentare diversi gruppi di clienti, come Ingrosso, Al dettaglio, Internet, Dipendenti, ecc.

Per creare un gruppo di clienti, completare i passaggi seguenti.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Clienti \> Gruppi di clienti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella casella **Gruppo di clienti** immettere un ID gruppo di clienti.
1. Immettere una descrizione appropriata nella casella **Descrizione**.
1. Immettere un valore appropriato nella casella **Termini di pagamento**.
1. Nella casella **Tempo tra la data di scadenza della fattura e la data di pagamento**, immettere un valore appropriato.
1. Nella casella **Gruppo imposta predefinito**, immettere un gruppo di imposta, se applicabile.
1. Selezionare la casella di controllo **Prezzi IVA inclusa** se applicabile.
1. Nella casella **Motivo di annullamento predefinito**, immettere un valore appropriato, se applicabile.

L'immagine seguente mostra diversi gruppi di clienti configurati.

![Gruppi di clienti.](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Creare una nuova rubrica clienti

Un cliente deve essere associato a una rubrica. Se una rubrica non è ancora stata creata, sarà necessario crearne una.

Per creare una rubrica clienti, procedere come segue.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Rubriche**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella casella **Nome** immettere un nome.
1. Nella casella **Descrizione** immettere una descrizione.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di rubrica.

![Rubrica.](media/address-book.png)

## <a name="create-a-default-customer"></a>Creare un cliente predefinito

Per creare un cliente predefinito, completare i passaggi seguenti.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Clienti \> Tutti i clienti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'elenco a discesa **Tipo** selezionare "Persona".
1. Nell'elenco a discesa **Conto cliente**, selezionare o inserire un numero di conto (ad esempio "100001").
1. Nell'elenco a discesa **Nome**, selezionare o inserire un nome (ad esempio, "Predefinito").
1. Nell'elenco a discesa **Secondo nome**, selezionare o inserire un nome (ad esempio, "Al dettaglio").
1. Nell'elenco a discesa **Cognome**, selezionare o inserire un nome (ad esempio, "Cliente").
1. Nell'elenco a discesa **Valuta**, selezionare o inserire una valuta (ad esempio, "USD").
1. Nell'elenco a discesa **Valuta**, selezionare il gruppo di clienti creato in precedenza.
1. Nell'elenco a discesa **Rubriche**, selezionare una rubrica clienti esistente.
1. Selezionare **Salva** per salvare e tornare alla schermata dei dettagli cliente per il nuovo cliente.

> [!NOTE]
> Non è necessario aggiungere un indirizzo per un cliente predefinito.

L'immagine seguente illustra un esempio di creazione di un cliente.

![Creazione di un cliente predefinito.](media/default-customer-creation.png)

L'immagine seguente mostra la configurazione di un cliente predefinito.

![Esempio di configurazione di un cliente.](media/default-customer-configuration1.png)

La maggior parte dei valori predefiniti nella schermata dei dettagli cliente può rimanere, ma è necessario modificare due valori.

1. Nella schermata dei dettagli cliente, espandere **Impostazioni predefinite ordine cliente**.
1. Nell'elenco a discesa **Sito**, selezionare o inserire un sito preconfigurato.
1. Nell'elenco a discesa **Magazzino**, selezionare o inserire un magazzino preconfigurato.

L'immagine seguente illustra un esempio di configurazione di un cliente.

![Esempio di configurazione di un cliente.](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Prerequisiti dell'impostazione dei canali](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
