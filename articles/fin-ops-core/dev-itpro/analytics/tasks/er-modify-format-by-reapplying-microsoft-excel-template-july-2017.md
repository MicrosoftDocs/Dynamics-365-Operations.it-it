---
title: Modificare i formati riapplicando i modelli di Excel
description: Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura "ER - Progettare una configurazione per la creazione di report nel formato OPENXML".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5b1bc5f227a0944c513dee2c12a5042decde872
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684237"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>Modificare i formati riapplicando i modelli di Excel

[!include [banner](../../includes/banner.md)]

Per completare i passaggi in questa procedura, è innanzitutto necessario completare la procedura "ER - Progettare una configurazione per la creazione di report nel formato OPENXML".

In questa procedura viene illustrato come modificare la configurazione ER riapplicando un modello di Microsoft Excel modificato. In questa procedura verrà importato un modello Excel modificato nelle configurazioni in formato ER create per la società di esempio, Litware, Inc. e verranno generati i documenti elettronici. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati GBSI. Prima di iniziare, scaricare e salvare il file, SampleVendPaymWsReport2.xlsx elencato nell'argomento della Guida "Modificare un formato per la creazione di report elettronici riapplicando un modello di Microsoft Excel" (modify-electronic-reporting-format-reapply-excel-template/).

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  

## <a name="select-the-er-format"></a>Selezionare il formato ER.
1. Fare clic su Configurazioni report.
2. Nella struttura espandere "Modello di pagamento".
3. Nella struttura selezionare "Modello di pagamento\Report foglio di lavoro di esempio".
4. Fare clic su Allegati.
    * Si noti che il file Excel SampleVendPaymWsReport.xlsx è attualmente utilizzato come modello per l'elaborazione del giornale di registrazione pagamenti.   
5. Fare clic su Apri.
    * Fare clic su Apri per visualizzare il layout del modello Excel.  
    * Esaminare il modello. Si noti che il modello include attualmente i dettagli relativi a ogni riga di pagamento, ovvero numero di conto del fornitore, nome del fornitore, banca, numero di registrazione, numero di conto, importi Dare e Avere e valuta. Per questo esempio, verrà esteso l'elenco aggiungendo i dettagli relativi alla data di pagamento.   
6. Chiudere la pagina.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Riapplicare un nuovo modello Excel al formato ER
1. Fare clic su Progettazione.
    * Aprire la versione bozza del formato ER selezionato da modificare.  
2. Nel Riquadro azioni fare clic su Importa.
3. Fare clic su Aggiornamento da Excel.
    * Fare clic su "Aggiorna modello", quindi selezionare il file SampleVendPaymWsReport2.xlsx.  
    * Fare clic su Aggiorna modello e cercare il file SampleVendPaymWsReport2.xlsx scaricato in precedenza.  
4. Fare clic su OK.
    * Il modello SampleVendPaymWsReport2.xlsx viene applicato. La struttura del formato ER verrà sincronizzata con il contenuto del modello, i cui elementi vengono aggiunti al formato ER. Tutti gli elementi presenti nel formato ER non inclusi nel modello verranno rimossi dalla definizione di formato.  
5. Nella struttura selezionare "Excel".
    * Si noti che il campo Modello ora contiene un riferimento al nuovo modello.   
6. Fare clic su Allegati.
7. Fare clic su Apri.
    * Fare clic su Apri per visualizzare il layout del modello Excel modificato.  
    * Esaminare il modello. Si noti che ora è presente una riga per la data di pagamento.   
8. Chiudere la pagina.
9. Nella struttura espandere "Excel".
10. Nella struttura espandere 'Excel\PaymLines'.
11. Nella struttura, selezionare "Excel\PaymLines\PaymDate".
    * Si noti che il formato ER ora contiene un nuovo elemento. Una cella, PaymDate, è stata aggiunta al modello Excel.  
12. Fare clic sulla scheda Mapping.
13. Nella struttura , espandere il "modello".
14. Nella struttura espandere "modello\Pagamenti".
15. Nella struttura selezionare "modello\Pagamenti\Data della transazione(TransactionDate)".
16. Fare clic su Associa.
    * Specificare i dati da aggiungere alla nuova cella in fase di esecuzione.  
17. Fare clic su Salva.
18. Chiudere la pagina.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Attivare la versione bozza modificata del formato ER da utilizzare per l'elaborazione del giornale di registrazione pagamenti
1. Nel riquadro azioni, fare clic su Configurazioni.
2. Fare clic su Parametri utente.
3. Selezionare Sì nel campo Esegui impostazioni.
4. Fare clic su OK.
5. Fare clic su Modifica.
6. Selezionare Sì nel campo Esegui bozza.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Utilizzare la versione bozza modificata del formato ER per l'elaborazione del giornale di registrazione pagamenti

Esaminare il foglio di lavoro creato che include il nuovo dettaglio delle righe di pagamento, ovvero la data di pagamento.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]