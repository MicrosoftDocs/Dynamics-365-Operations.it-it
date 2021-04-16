---
title: Ritenuta d'acconto in transazioni di acquisto
description: Per i fornitori soggetti a ritenuta d'acconto, puoi assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Tutti i fornitori**.
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
ms.openlocfilehash: faeaf0746532875d3517a208c9c338c112bf2c77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816885"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Ritenuta d'acconto in transazioni di acquisto

Per i fornitori soggetti a ritenuta d'acconto, puoi assegnare il **gruppo di ritenuta d'acconto** predefinito nella pagina **Tutti i fornitori**.

1. Vai a **Pannello di navigazione > Moduli > Contabilità fornitori > Fornitori > Tutti i fornitori**.

2. Fai clic sul rispettivo conto fornitore, fai clic su **Modifica**.

3. Nella scheda **Fattura e consegna**, imposta il campo **Calcola ritenuta d'acconto** su **Sì**.

   > [!NOTE] 
   > La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è attivata per questo fornitore nei dati.

4. Seleziona un gruppo ritenuta d'acconto in **Gruppo ritenuta d'acconto**.

5. Fare clic su **Salva**.

Per articoli/servizi soggetti a ritenuta d'acconto puoi assegnare l'impostazione predefinita **Gruppo ritenuta d'acconto articolo** in **Prodotti rilasciati**.

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.

2. Fai clic sul rispettivo numero articolo, quindi su **Modifica**.

3. Nella scheda **Acquisto**, fai clic su **Calcola ritenuta d'acconto**.

   > [!NOTE] 
   > La ritenuta d'acconto non sarà calcolata se **Calcola ritenuta d'acconto** non è impostata su **Sì** per questo articolo nella scheda **Acquisto** nella pagina **Prodotto rilasciato**.

4. Seleziona un gruppo ritenuta d'acconto articolo nell'elenco **Gruppo ritenuta d'acconto articolo**.

5. Fare clic su **Salva**.

I gruppi di ritenute d'acconto e ritenute d'acconto articoli possono essere assegnati nelle pagine: 

- **Ordine fornitore**
- **Fattura fornitore**
- **Giornale di registrazione fatture**

Il gruppo ritenuta d'acconto e gruppo ritenuta d'acconto articolo predefiniti verranno riportati nelle righe durante la creazione **Ordini di acquisto** e/o **Fatture fornitore in sospeso**. Per **Giornale di registrazione fatture**, puoi cambiare **Calcola ritenuta d'acconto** e seleziona **Gruppo ritenuta d'acconto articolo** nella scheda **Generale** del giornale.

L'importo temporaneo della ritenuta d'acconto è disponibile nel campo **Ritenuta d'acconto rettificata** della scheda **Totali** nella pagina **Ordine d'acquisto**.

![La ritenuta d'acconto è inclusa nell'ordine d'acquisto](media/withholding-tax-adjusted.png)

La ritenuta d'acconto viene calcolata su **Giornale di registrazione pagamenti fornitore**. Puoi modificare manualmente i codici della ritenuta d'acconto applicabile, nonché gli importi effettivi della ritenuta d'acconto nella scheda **Ritenuta d'acconto** nella pagina **Liquida transazioni**.

![La ritenuta può essere regolata manualmente nella pagina Liquidazione transazioni](media/withholding-tax-vendor-payment-tab.png)

L'importo della ritenuta d'acconto derivato verrà detratto dal pagamento del fornitore e registrato nel conto **Conto della ritenuta d'acconto** in un voucher correlato.

![Conto ritenuta d'acconto con relativo giustificativo](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]