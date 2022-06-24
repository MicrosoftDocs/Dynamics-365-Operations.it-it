---
title: Calcolare le fatture TDS utilizzando il modulo di ordine fornitore e il modulo di ordine cliente
description: In questo articolo sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) su vari tipi di fatture.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 72883741ee7eed6b0296736c80dd648c882ae53e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853287"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Calcolare le fatture TDS utilizzando il modulo di ordine fornitore e il modulo di ordine cliente

[!include [banner](../includes/banner.md)]

In questo articolo sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) su vari tipi di fatture utilizzando le pagine **Ordine fornitore**, **Giornale di registrazione acquisti**, **Ordine programmato** e **Ordine cliente**.

1. Crea un ordine fornitore, un giornale di registrazione acquisti, un ordine programmato di acquisto o un ordine cliente utilizzando la pagina elencata. Immetti i dettagli richiesti.

2. Seleziona la scheda **Imposta** per visualizzare la natura del soggetto valutato del fornitore o del cliente. Queste informazioni sono elencate nel campo **Natura soggetto valutato**, sotto il gruppo di campi **Gruppo ritenute d'acconto**.

3. Nel campo **Gruppo TDS**, visualizza o modifica il gruppo TDS predefinito definito per il fornitore o il cliente.

   > [!NOTE]
   > Il campo **Gruppo TCS** non è disponibile quando si seleziona un gruppo TDS nel campo **Gruppo TDS**. La TDS viene calcolata solo se la casella di controllo **Calcola ritenuta d'acconto** è selezionata per il fornitore o il cliente nella pagina **Tutti i fornitori** o **Tutti i clienti**.  

4. Crea righe articolo nella scheda **Righe** e immetti i dettagli richiesti.

5. Seleziona la scheda **Imposta** (a livello di riga) per visualizzare o modificare il gruppo TDS definito a livello di intestazione. Il gruppo TDS viene visualizzato nel campo **Gruppo TDS**, che si trova sotto il gruppo di campi **Gruppo ritenute d'acconto**.

6. Seleziona la scheda **Informazioni fiscali** e seleziona indirizzi alternativi impostati per il nome della società visualizzato in questo campo. Il nome della società viene visualizzato nel campo **Nome**, che si trova sotto il gruppo di campi **Informazioni società**. 

   Il TAN del nome di società selezionato è visualizzato nel campo **Numero di conto imposta** (**TAN**), sotto il gruppo di campi **Ritenuta d'acconto**. 

7. Seleziona **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**. Visualizza i seguenti campi nel riquadro superiore della pagina **Transazioni ritenuta d'acconto temporanee**.

   - **Importo** **ritenuta** **d'acconto** **in** **totale** - La TDS totale calcolata per la transazione per il gruppo TDS.

   - **Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione. La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.

   - **Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.

   - **TDS** - Se selezionato, un gruppo TDS viene associato alla transazione.

I campi nelle schede **Panoramica**, **Generale** e **Rettifica** nella pagina **Transazioni ritenuta d'acconto temporanee** visualizza dettagli sull'importo TDS calcolato e sull'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.

8. Seleziona **Soglia** per aprire la pagina **Soglia**. Visualizza il limite di soglia definito per il componente fiscale TDS associato a un codice fiscale TDS specifico in questa pagina.

9. Seleziona **Designer formula** per aprire la pagina **Designer formula**. Visualizza la formula definita per un codice imposta TDS specifico in questa pagina. 

10. Registrare la fattura. L'importo TDS calcolato sulle fatture di acquisto viene registrato in un conto fornitori e l'importo TDS calcolato sulle fatture di vendita viene registrato in un conto clienti per ogni codice imposta TDS nel gruppo TDS. I conti clienti o fornitori per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.

11. Seleziona il pulsante **Richiesta info** **> Fattura > pulsante Ritenuta d'acconto registrata** per aprire la pagina **Transazioni ritenuta d'acconto**. Puoi visualizzare la percentuale totale utilizzata per calcolare la TDS per la transazione nel campo **Valore**.

I campi nelle schede **Panoramica**, **Generale** e **Importo** nella pagina **Transazioni ritenuta d'acconto** visualizza le informazioni della TDS calcolata per la transazione. Visualizza le informazioni sul calcolo della TDS per ogni codice imposta TDS associato al gruppo TDS.
