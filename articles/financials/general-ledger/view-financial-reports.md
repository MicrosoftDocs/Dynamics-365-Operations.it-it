---
title: Visualizza report finanziari
description: In questo articolo viene descritto come visualizzare ed esplorare i report finanziari in Microsoft Dynamics 365 for Finance and Operations. Include informazioni sulle varie opzioni che è possibile applicare ai report finanziari per modificare l'aspetto e i dati inclusi.
author: kweekley
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a939ce2f43645963392363fc6452f8bc55bd963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "312947"
---
# <a name="view-financial-reports"></a>Visualizza report finanziari

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come visualizzare ed esplorare i report finanziari in Microsoft Dynamics 365 for Finance and Operations. Include informazioni sulle varie opzioni che è possibile applicare ai report finanziari per modificare l'aspetto e i dati inclusi.

<a name="financial-reporting-overview"></a>Panoramica sui report finanziari
----------------------------

## <a name="open-a-financial-report"></a>Aprire un report finanziario
Per aprire un report, selezionare il nome del report. La prima volta che un report viene aperto, viene generato automaticamente per il mese precedente. Ad esempio, se si apre un report per la prima volta nell'agosto 2015, il report viene generato per il 31 luglio 2015. Dopo l'apertura di un report, puoi iniziare a esplorarlo eseguendo il drill-down su parti specifiche di dati e modificando le opzioni di report.

## <a name="drill-down-on-a-financial-report"></a>Eseguire il drill-down su un report finanziario
I report finanziari possono includere più livelli di dettaglio. Il livello finanziario è il primo livello che si nota quando si apre un report finanziario. Per accedere al livello di account, selezionare i dati su cui eseguire il drill-down. Ad esempio, per visualizzare i dettagli del conto per le vendite, selezionare i dati di vendita che si desidera esplorare. Dal livello di conto è possibile eseguire il drill-down per visualizzare le transazioni che costituiscono il saldo del conto. Sono disponibili due metodi per visualizzare le transazioni: transazioni report e transazioni giustificativo.

-   **Transazioni report**: le transazioni appaiono in una visualizzazione formattata che è inclusa nel report finanziario. Per visualizzare le transazioni nella visualizzazione formattata, selezionare i dati su cui eseguire il drill-down e fare clic su **Drill-down a livello di transazione report**.
-   **Transazioni giustificativo**: una richiesta di informazioni su transazioni giustificativo viene aperta, in cui è possibile visualizzare le transazioni. Per visualizzare le transazioni nella richiesta di informazioni su transazioni giustificativo, selezionare i dati su cui eseguire il drill-down e fare clic su **Apri transazioni di acconto**.

Se i dati sono dati del budget, è possibile scegliere di aprire le voci contabili del budget. Per chiudere uno dei livelli del report e tornare al punto di partenza, è possibile premere il tasto Esc o fare clic sul pulsante **Chiudi** (**X**) in alto a destra.

## <a name="change-report-options"></a>Cambiare le opzioni del report
È possibile modificare la data del report, applicare filtri di dimensione e di attributo, o modificare lo scenario del budget di un report **Effettivi rispetto al budget**. Nel Riquadro azioni fare clic su **Opzioni report** e seguire uno o più dei seguenti passaggi:

-   Per modificare il periodo base e l'anno base di un report, selezionare un periodo base e un anno base, quindi fare clic su **OK**.
-   Per applicare filtri di attributi a un report, selezionare **Aggiungere un filtro attributi**. Selezionare il tipo di attributo, immettere il valore attributo, quindi fare clic su **OK**. Ad esempio, se si seleziona l'attributo **Categoria conti**, immettere **VENDITE** come valore di attributo. Per rimuovere un filtro di attributo, fare clic su **Cancella**.
-   Per applicare filtri di dimensioni a un report,  selezionare **Aggiungere un filtro dimensioni**. Selezionare la dimensione e quindi digitare l'ID dimensione o selezionare la dimensione nell'elenco. Per rimuovere un filtro dimensione, fare clic su **Cancella**.
-   Per modificare lo scenario su un report **Effettivi rispetto al budget**, selezionare un nuovo scenario, quindi fare clic su **OK**. Se lo scenario selezionato è relativo a un anno diverso, assicurarsi di aggiornare l'anno di base. Ad esempio, se lo scenario corrente è per l'anno fiscale 2015 e si seleziona un nuovo scenario che è per l'anno fiscale 2016, si dovrà modificare l'anno base su **2016**.

Quando si fa clic su **OK**, tutte le opzioni selezionate sono applicate al report. Se si decide che non si desidera applicare le opzioni selezionate, fare clic su **Annulla**.

## <a name="update-a-financial-report"></a>Aggiornare un report finanziario
È possibile aggiornare (aggiornamento) un report finanziario in modo da visualizzare i dati più recenti per il periodo e l'anno in cui il report è stato generato. Ad esempio, se si aggiorna un report finanziario generato per l'ottobre 2015, il report riflette le nuove transazioni registrate per l'ottobre 2015. Per aggiornare un report finanziario, nel Riquadro azioni fare clic su **Aggiorna**. Un report aggiornato è disponibile solo per la persona che l'ha aggiornato. Perché altre persone visualizzino gli stessi dati, il report deve essere pubblicato.

## <a name="publish-a-financial-report"></a>Pubblicare un report finanziario
Dopo avere aggiornato un report finanziario, è possibile pubblicarlo. Altre persone dell'organizzazione potranno quindi visualizzarlo. Per pubblicare un report, nel Riquadro azioni fare clic su **Pubblica**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Visualizzare un report finanziario in una valuta diversa
Un report finanziario può essere visualizzato in qualsiasi valuta in qualsiasi momento. Per visualizzare un report in una valuta diversa, nel Riquadro azioni fare clic su **Valuta**, quindi selezionare una valuta. Il report viene convertito nella valuta e i risultati vengono visualizzati. Tutti i codici valuta o simboli inclusi come parte della progettazione del report vengono aggiornati in modo da riflettere la nuova valuta. Le valute visualizzate nell'elenco sono le valute di dichiarazione configurate in Finance and Operations.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Visualizzare una visualizzazione riepilogativa del report finanziario
Un report finanziario può contenere le righe di dettaglio e le righe riepilogative. Le righe di dettaglio sono righe contenenti i conti principali o le dimensioni. Le righe riepilogative sono descrizione, totale e righe di calcolo. Per visualizzare solo le righe riepilogative di un report, fare clic su **Mostra**, quindi su **Solo righe di riepilogo**. Il report viene compresso e visualizza solo le righe riepilogative. Per visualizzare le righe di dettaglio insieme alle righe di riepilogo, fare clic su **Mostra**, quindi di nuovo su **Solo righe di riepilogo**.

## <a name="open-a-financial-report-from-a-previous-month"></a>Aprire un report finanziario di un mese precedente
È possibile visualizzare i report per il mese corrente o i mesi precedenti senza rigenerare il report. Per aprire il report per un mese precedente, fare clic su **Mostra** quindi fare clic su **Report precedenti**. Un elenco dei mese precedenti per cui il report viene generato viene visualizzato. Espandere il mese di cui visualizzare il report, selezionare la data, quindi fare clic su **OK**. Viene visualizzato il report per il mese precedente. Per tornare al report del mese corrente, fare clic su **Annulla**.

## <a name="print-a-financial-report"></a>Stampare un report finanziario
Per stampare un report finanziario, nel Riquadro azioni fare clic su **Stampa**, quindi completare uno o più dei passaggi riportati di seguito per impostare le opzioni di stampa:

-   Per includere diversi livelli di dettaglio nel report stampato, impostare il dispositivo di scorrimento su **Sì** o **No**. Se un report utilizza una struttura gerarchica, è possibile scegliere di includere tutti i punti di rilevazione o solo il punto di rilevazione corrente.
-   Per impostare le dimensioni della pagina, selezionare le dimensioni della pagina nell'elenco.
-   Per impostare il layout di pagina, selezionare un layout nell'elenco. Se si desidera che il contenuto del report si adatti alla larghezza selezionata, impostare il dispositivo di scorrimento su **Sì**.
-   Per impostare i margini di pagina, immettere la dimensione dei margini superiore, inferiore, sinistro e destro in pollici.

Dopo aver completato l'impostazione delle opzioni di stampa, fare clic su **Stampa** per stampare il report. Se si decide che non si desidera stampare il report, fare invece clic su **Annulla**. Viene visualizzata un'anteprima del report stampato. È possibile selezionare la stampante alla quale inviare il report ed è inoltre possibile rettificare le opzioni di stampa.

## <a name="export-a-financial-report"></a>Esportare un report finanziario
Per esportare un report finanziario, nel Riquadro azioni fare clic su **Esporta**. Il report viene esportato in Microsoft Excel e il browser chiede di aprire o salvare il file esportato. Le impostazioni di esportazione definite nella progettazione del report vengono applicate al report esportato.    

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Report finanziari per Microsoft Dynamics AX](../../dev-itpro/analytics/financial-reporting-intro.md)




