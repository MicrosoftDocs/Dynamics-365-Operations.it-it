---
title: Ritenuta d'acconto in transazioni di vendita
description: Questo argomento elenca i passaggi per evitare il calcolo della ritenuta d'acconto per i clienti selezionati. Per i clienti che specificano la ritenuta d'acconto nei loro pagamenti, è possibile assegnare il gruppo di ritenuta d'acconto predefinito.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: b221fc04ef82f148846fc0c282f6c8601f0eb4759d99a8dee02256cc0d42417f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747085"
---
# <a name="withholding-tax-in-sales-transactions"></a>Ritenuta d'acconto in transazioni di vendita

Questo argomento elenca i passaggi per evitare il calcolo della ritenuta d'acconto per i clienti selezionati. Per i clienti che specificano la ritenuta d'acconto nei loro pagamenti, è possibile assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Clienti**. 

1. Vai a **Pannello di navigazione > Moduli > Contabilità clienti > Clienti > Tutti i clienti**.

2. Fai clic sul rispettivo conto cliente, fai clic su **Modifica**.

3. Nella scheda **Fattura e consegna**, imposta il campo **Calcola ritenuta d'acconto** su **Sì**.

   > [!NOTE] 
   > La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è attivata per questo cliente nei dati master.

4. Seleziona un gruppo ritenuta d'acconto in **Gruppo ritenuta d'acconto**.

5. Fare clic su **Salva**.

Per articoli/servizi soggetti a ritenuta d'acconto puoi assegnare l'impostazione predefinita **Gruppo ritenuta d'acconto articolo** in **Prodotti rilasciati**.

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.

2. Fai clic sul rispettivo numero articolo, quindi su **Modifica**.

3. Nella scheda **Vendi**, fai clic su **Calcola ritenuta d'acconto**.

   > [!NOTE] 
   > La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è impostata su **Sì** per questo articolo nella scheda **Vendita** nella pagina **Prodotto rilasciato**.

4. Seleziona un gruppo ritenuta d'acconto articolo nell'elenco **Gruppo ritenuta d'acconto articolo**.

5. Fare clic su **Salva**.

I gruppi di ritenute d'acconto e ritenute d'acconto articoli possono essere assegnati utilizzando la pagina **Ordine cliente**. 

Il Gruppo ritenute d'acconto e il Gruppo ritenuta d'acconto articolo predefiniti verranno utilizzati come voci predefinite nelle righe ordini di vendita quando si crea un nuovo ordine di vendita.

La ritenuta d'acconto viene calcolata e registrata con **Giornale di registrazione pagamenti cliente**. Puoi modificare manualmente il codice della ritenuta d'acconto applicabile, nonché l'importo effettivo della ritenuta d'acconto nella scheda **Ritenuta d'acconto** nella pagina **Liquida transazioni**.

L'importo della ritenuta d'acconto calcolato verrà detratto dal pagamento del cliente e registrato nel conto **Compensazione della ritenuta d'acconto** in un voucher correlato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]