---
title: L'IVA negli ordini online è calcolata in modo errato
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'IVA negli ordini online viene calcolata in modo errato o quando la fascia IVA nella riga di vendita non è impostata correttamente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021105"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>L'IVA negli ordini online è calcolata in modo errato

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando l'IVA negli ordini online viene calcolata in modo errato o quando la fascia IVA nella riga di vendita non è impostata correttamente.

## <a name="description"></a>Descrizione

Quando viene effettuato un ordine di e-commerce, l'IVA viene calcolata in modo errato o la fascia IVA nella riga di vendita è impostata in modo errato.

## <a name="resolution"></a>Risoluzione

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Configurare l'IVA per un punto vendita al dettaglio in Commerce Headquarters

Per configurare l'IVA per un punto vendita al dettaglio in Commerce Headquarters, procedere come segue.

1. Selezionare **Retail e Commerce \> Canali \> Tutti i punti vendita**.
1. Selezionare il punto vendita per configurare l'IVA.
1. Nella Scheda dettaglio **Generale**, nella sezione **IVA**, configurare le informazioni sull'IVA per il punto vendita.

> [!NOTE]
> Per il ritiro del prodotto presso un punto vendita, la fascia IVA proviene dal punto vendita selezionato per il ritiro. Per ulteriori informazioni, vedere [Impostare altre opzioni IVA per i punti vendita](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Configurare l'IVA per l'indirizzo di un cliente in Commerce Headquarters

Per configurare l'IVA per l'indirizzo di un cliente in Commerce Headquarters, procedere come segue.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Selezionare il cliente per cui configurare l'IVA.
1. Nella Scheda dettaglio **Indirizzi** selezionare l'indirizzo per cui configurare l'IVA, selezionare **Altre opzioni** e quindi selezionare **Avanzate**.
1. Nella Scheda dettaglio **Generale**, selezionare la **Fascia IVA**.
1. Nel capo **Fascia IVA** selezionare il valore appropriato.

> [!NOTE]
> Per la spedizione che comporta l'IVA nell'indirizzo del cliente, l'indirizzo di consegna della riga determina la fascia IVA per la riga. Se il cliente effettua la spedizione a un indirizzo esistente con una fascia IVA già configurata, verrà utilizzata la fascia IVA esistente. Per impostazione predefinita, gli indirizzi non hanno una fascia IVA quando vengono creati.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Configurare le fasce IVA generali in Commerce Headquarters

Per configurare fasce IVA generali in Commerce Headquarters, seguire questi passaggi.

1. Selezionare **Imposta \> Imposte indirette \> IVA \> Fascia IVA**.
1. Nel riquadro di spostamento a sinistra, selezionare la fascia IVA da configurare.
1. Nella Scheda dettaglio **Imposta in base alla destinazione vendita al dettaglio**, configurare le imposte per la fascia IVA.

> [!NOTE]
> Per la spedizione che non prevede l'IVA nell'indirizzo del cliente, l'indirizzo di consegna della riga e le imposte basate sulla destinazione configurate per la fascia IVA determinano la fascia IVA. Per ulteriori informazioni, vedere [Impostare le imposte per i punti vendita online in base alla destinazione](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare l'IVA per gli ordini online](../sales-tax-config.md)