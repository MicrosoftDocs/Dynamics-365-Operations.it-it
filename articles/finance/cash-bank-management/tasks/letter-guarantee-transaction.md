---
title: Transazione lettera di garanzia
description: In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 786aecf69bae3d07ac80a55b4dc835dd8129bd59
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803966"
---
# <a name="letter-of-guarantee-transaction"></a>Transazione lettera di garanzia

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per il processo della lettera di garanzia.



Completare le seguenti attività prima di eseguire questa procedura:

- Impostare le linee di credito bancarie e i profili registrazione per una lettera di garanzia.

- Creare un contratto per linea di credito bancaria per una lettera di garanzia.



Questa procedura utilizza la società dimostrativa USMF.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Creare un ordine cliente con lettera di garanzia
1. Andare a **Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto cliente**, immettere o selezionare un valore.
4. Espandere la sezione **Generale**.
5. Nel campo **Sito** immettere o selezionare un valore.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo **Magazzino** immettere o selezionare un valore.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Selezionare **Lettera di garanzia** nel campo **Tipo di documento bancario**.
10. Fare clic su **OK**.
11. Nel campo **Numero articolo** immettere o selezionare un valore.
12. Immettere un numero nel campo **Prezzo unitario**.
13. Espandere la sezione **Dettagli riga**.
14. Fare clic sulla scheda **Consegna**.

>[!Note] 
>Seleziona **Controllo data di consegna** = **Nessuno**  

15. Nel campo **Data di spedizione richiesta** immettere una data.
16. Nel campo **Data di spedizione confermata** immettere una data.

## <a name="process-letter-of-guarantee_request"></a>Elaborare la lettera di garanzia: Richiesta
1. Nel riquadro azioni fare clic su **Gestisci**.
2. Fare clic su **Lettera di garanzia**.
3. Nel Riquadro azioni, fare clic su **Lettera di garanzia**.
4. Fare clic su **Richiesta** per aprire la finestra di dialogo a discesa.
5. Nel campo **Tipo** immetti o seleziona un valore.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo **Valore** immettere un numero.
8. Nel campo **Data di scadenza** immettere una data e un'ora.
9. Fare clic su **OK**.
10. Chiudere la pagina.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Elaborare la lettera di garanzia: Invia a banca
1. Fare clic su **Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Fare clic su **Invia a banca** per aprire la finestra di dialogo a discesa.
4. Nel campo **Conto bancario** immettere o selezionare un valore.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su **OK**.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Elaborare la lettera di garanzia: Ricevi da banca
1. Fare clic su **Ricevi da banca** per aprire la finestra di dialogo a discesa.
2. Digitare un valore nel campo **Numero banca**.
    * Verificare i valori nei campi calcolati di **spesa** e **margine**.  
3. Fare clic su **OK**.
4. Espandere la sezione **Azioni**.
    * Verificare il record 'Ricevi da banca'.  
5. Fare clic per seguire il collegamento nel campo **Numero batch giornale di registrazione**.
6. Fare clic su **Righe**.
    * Verificare la registrazione delle scritture contabili.  
7. Chiudere la pagina.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Elaborare la lettera di garanzia: Assegna al beneficiario
1. Andare a **Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
3. Nel riquadro azioni fare clic su **Gestisci**.
4. Fare clic su **Lettera di garanzia**.
5. Nel Riquadro azioni, fare clic su **Lettera di garanzia**.
6. Fare clic su **Assegna al beneficiario** per aprire la finestra di dialogo a discesa.
7. Fare clic su **OK**.
8. Fare clic su **Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia**.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Fare clic su **Assegna al beneficiario** per aprire la finestra di dialogo a discesa.
11. Fare clic su **OK**.
12. Espandere la sezione **Azioni**.
    * Convalidare il record 'Assegna al beneficiario'.  

## <a name="process-letter-of-guarantee_increase-value"></a>Elaborare la lettera di garanzia: Aumenta valore
1. Andare a **Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
3. Nel riquadro azioni fare clic su **Gestisci**.
4. Fare clic su **Lettera di garanzia**.
5. Nel Riquadro azioni, fare clic su **Lettera di garanzia**.
6. Fare clic su **Aumenta valore** per aprire la finestra di dialogo a discesa.
7. Nel campo **Valore da aggiungere** immettere un numero.
8. Fare clic su **OK**.
9. Fare clic su **Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia**.
10. Nell'elenco trovare e selezionare il record desiderato.
11. Fare clic su **Aumenta valore** per aprire la finestra di dialogo a discesa.
12. Fare clic su **OK**.
13. Espandere la sezione **Azioni**.
    * Verificare il record 'Aumenta valore'.  
14. Nell'elenco trovare e selezionare il record desiderato.
15. Fare clic per seguire il collegamento nel campo **Numero batch giornale di registrazione**.
16. Fare clic su **Righe**.
    * Verificare la scritture contabili registrate.  

## <a name="process-letter-of-guarantee_liquidate"></a>Elaborare la lettera di garanzia: Liquida
1. Andare a **Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
3. Nel riquadro azioni fare clic su **Gestisci**.
4. Fare clic su **Lettera di garanzia**.
5. Nel Riquadro azioni, fare clic su **Lettera di garanzia**.
6. Fare clic su **Liquida** per aprire la finestra di dialogo a discesa.
7. Fare clic su **OK**.
8. Fare clic su **Gestione cassa e banche > Lettere di garanzia > Lettere di garanzia**.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Fare clic su **Liquida** per aprire la finestra di dialogo a discesa.
11. Fare clic su **OK**.
12. Espandere la sezione **Azioni**.
    * Verificare il record 'Liquida'.  
13. Nell'elenco trovare e selezionare il record desiderato.
14. Fare clic per seguire il collegamento nel campo **Numero batch giornale di registrazione**.
15. Fare clic su **Righe**.
    * Verificare la scritture contabili registrate.  
16. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
