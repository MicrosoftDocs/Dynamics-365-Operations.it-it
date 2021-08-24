---
title: Calcolare la TDS sulle fatture utilizzando giornali di registrazione
description: In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) nei giornali di registrazione.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: cfe473f39ee729957924fd7c161aed01138cd507eea56766af35177891676f65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778895"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Calcolare la TDS sulle fatture utilizzando giornali di registrazione

[!include [banner](../includes/banner.md)]

In questo argomento sono elencati i passaggi per il calcolo dell'imposta dedotta all'origine (TDS) nei giornali di registrazione.

Inizia aprendo la pagina **Giornali di registrazione generali** (**Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**).

[![Giornali di registrazione generali.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Crea righe di giornale di registrazione utilizzando i moduli del giornale di registrazione elencati nella tabella. Seleziona il tipo di conto e il tipo di conto di contropartita e inserisci l'importo per la transazione. 

   > [!NOTE]
   > Nella pagina **Giornale di approvazione fatture**, seleziona **Trova giustificativi** e seleziona le fatture su cui calcolare la TDS. Visualizza le fatture create nella pagina **Registro fatture** o la pagina **Trova giustificativi**.  

2. Nella scheda **Generale** della pagina **Giustificativo giornale di registrazione**, visualizza o modifica il gruppo TDS definito per il fornitore o il cliente nel campo **Gruppo TDS**. L'importo TDS calcolato sulle righe del giornale di registrazione si basa sulla formula definita per i codici imposta TDS elencati nel campo **Gruppo TDS**. 

   > [!NOTE]
   > Il campo **Gruppo ritenute d'acconto** e il campo **Gruppo TCS** non sono disponibili quando selezioni un gruppo TDS nel campo **Gruppo TDS**. Il campo **Gruppo ritenute d'acconto** è disponibile solo nella pagina **Giornale di registrazione generale**. La TDS viene calcolata solo se la casella di controllo **Calcola ritenuta d'acconto** è selezionata per il fornitore o il cliente nelle pagine **Tutti i fornitori** o **Tutti i clienti**.   

3. Seleziona la scheda **Informazioni fiscali**. Se necessario, seleziona gli indirizzi alternativi di una società impostati per la società in questo campo. Puoi visualizzare il nome della società nel campo **Nome**, che si trova sotto il gruppo di campi **Informazioni società**. 

4. Visualizza la natura della categoria di soggetto valutato del fornitore o del cliente nel campo **Natura soggetto valutato** sotto il gruppo di campi **Ritenuta d'acconto**. Nel campo **Numero conto imposta** (**TAN**), visualizza il TAN del nome di società selezionato che viene visualizzato.  

5. Seleziona **Ritenuta d'acconto** nel menu **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**. I seguenti campi sono visualizzati nel riquadro superiore della pagina **Transazioni ritenuta d'acconto temporanee**.

   - **Importo ritenuta d'acconto in totale** - La TDS totale calcolata per la transazione per il gruppo TDS.

   - **Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione. La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.

   - **Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.

   - **TDS** - Se selezionato, un gruppo TDS viene associato alla transazione.

  I campi nelle schede **Panoramica**, **Generale** e **Rettifica** nella pagina **Transazioni ritenuta d'acconto temporanee** visualizza dettagli sull'importo TDS calcolato e sull'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.

6. Seleziona **Soglia** per aprire la pagina **Soglia**. Visualizza il limite di soglia e il limite di soglia di eccezione definiti per il componente fiscale TDS associato a uno specifico codice imposta TDS in questa pagina.

   Seleziona **Designer formula** per aprire il modulo **Designer formula**. Visualizza la formula definita per uno specifico codice imposta TDS in questa pagina. Chiudi le pagine **Designer formula** e **Transazioni ritenuta d'acconto temporanee** per tornare alla pagina **Giustificativo giornale di registrazione**.

8. Immetti gli altri dettagli necessari. Convalida e registra il giornale di registrazione. L'importo TDS calcolato sulle fatture di acquisto viene registrato nel conto fornitori. L'importo TDS calcolato sulle fatture di vendita viene registrato nel conto clienti definito per ogni codice imposta TDS nel gruppo TDS. I conti clienti o fornitori per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.

9. Seleziona **Ritenuta d'acconto registrata** per aprire la pagina **Transazioni** **ritenuta** **d'acconto**. Nel campo **Valore** viene visualizzata la percentuale totale utilizzata per calcolare la TDS per la transazione.

   I campi nelle schede **Panoramica**, **Generale** e **Importo** nella pagina Transazioni ritenuta d'acconto visualizza dettagli sull'importo TDS calcolato e sull''importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.
