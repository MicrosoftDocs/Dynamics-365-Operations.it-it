---
title: Creare un nuovo accordo commerciale
description: Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico.
author: omulvad
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4319f6b117df38379c88aa8fa06c0f93b3eb917852af3c6461c1d12ead11ecc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773155"
---
# <a name="create-a-new-trade-agreement"></a>Creare un nuovo accordo commerciale

[!include [banner](../../includes/banner.md)]

Questa procedura illustra come creare un accordo commerciale in cui si registra un nuovo prezzo di vendita del prodotto accordato con un cliente specifico. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Se si utilizzano i propri dati, prima di iniziare questa guida è necessario assicurarsi che sia presente un nome di giornale di registrazione per accordi commerciali in cui la relazione predefinita sia impostata su "Prezzo (vend.)".

## <a name="create-and-post-a-new-trade-agreement-journal"></a>Creare e registrare un nuovo giornale di registrazione degli accordi commerciali

1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Prezzi e sconti > Giornali di registrazione accordi commerciali**.
2. Fare clic su **Nuovo**.
3. Nel campo **Nome** fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco trovare e selezionare il record desiderato.
5. In **Riquadro azioni** fai clic su **Righe**.
6. Nel campo **Codice conto** selezionare "Tabella".
    
    In questo esempio viene aggiornato il prezzo per un cliente specifico ed è pertanto necessario scegliere Tabella. Se si aggiorna il prezzo di listino del prodotto, è necessario selezionare "Tutti", in modo che il nuovo prezzo sia valido per tutti i clienti. Se si differenziano i prezzi per segmenti di clienti diversi, è necessario selezionare Gruppo. Per selezionare Gruppo, è necessario impostare i gruppi di prezzi del cliente.  

7. Nel campo **Selezione del conto** fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco trovare e selezionare il record desiderato.
9. Nel campo **Codice articolo** selezionare "Tabella".
    
    Quando si immette un accordo commerciale di tipo "Prezzo (vend.)", è necessario selezionare "Tabella" nel campo **Codice articolo**. Ciò è dovuto al fatto che un prezzo è un valore assoluto e non può essere lo stesso per tutti i prodotti o per un gruppo di prodotti.
    
10. Nel campo **Relazione articolo** fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco selezionare il prodotto da includere nell'accordo. Prendere nota del prodotto selezionato.  
12. Nel campo **Da** immettere una quantità minima.
    - Se il cliente deve ordinare una quantità minima prima di ottenere il nuovo prezzo, è necessario specificare la quantità in questo campo.  
    - Immettere un valore nel campo **A** per specificare la quantità massima sopra cui il prezzo del contratto non sarà valido. Se si offrono prezzi e sconti in base a più intervalli di quantità, specificare ogni intervallo come una coppia di quantità minima e massima nel campo **Da** e **A** rispettivamente.
13. Nel campo **Importo in valuta** immettere un prezzo.
14. Sotto la sezione **Dettagli**, nel campo **Dal** immettere una data di inizio validità dell'accordo.
15. Fare clic su **Salva**.
16. Fare clic su **Convalida**.
17. Fare clic su **Convalida le righe selezionate**.
18. Fare clic su **OK**.
19. Fare clic su **Registra**.
20. Fare clic su **OK**.

## <a name="view-trade-agreements-for-a-product"></a>Visualizzare accordi commerciali per un prodotto

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
2. Nell'elenco individuare e selezionare il prodotto il cui prezzo è stato aggiornato.
3. Nel **riquadro azioni** fare clic su **Vendi**.
4. Fare clic su **Visualizza accordi commerciali**.
    
    Esaminare i dettagli dell'accordo commerciale sui prezzi creato.

5. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="whitepaper"></a>White paper

Per ulteriori informazioni, scarica il seguente white paper (scritto per supportare AX2012, ma è ancora valido per Dynamics 365 Supply Chain Management)

- [Accordi commerciali](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>Blog della community

- [Prezzi di vendita in Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]