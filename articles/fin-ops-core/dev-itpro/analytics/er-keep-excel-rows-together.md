---
title: Progettare un formato ER per tenere insieme le righe sulla stessa pagina di Excel
description: In questo articolo viene illustrato come progettare un formato di report elettronico (ER) che mantenga le righe insieme nella stessa pagina di Microsoft Excel.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 98e6dd4f926908f65239f3e4f3608f9c9408f9d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854671"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Progettare un formato ER per tenere insieme le righe sulla stessa pagina di Excel

[!include [banner](../includes/banner.md)]


Questo articolo spiega come un utente con il ruolo di Amministratore di sistema o Consulente funzionale per la [creazione di report elettronici](general-electronic-reporting.md) può configurare un [formato](er-overview-components.md#format-component) che genera documenti in uscita in Microsoft Excel e gestisce l'impaginazione dei documenti in modo che le righe create vengano mantenute nella stessa pagina.

In questo esempio, modificherai il formato ER fornito da Microsoft utilizzato per stampare fatture a testo libero in Excel. Le tue modifiche ti permetteranno di gestire l'impaginazione di un report di fattura a testo libero generato in modo che tutte le righe di una singola riga di fattura vengano mantenute sulla stessa pagina quando possibile.

Le procedure in questo articolo possono essere completate nella società **USMF**. Non è richiesta alcuna codifica.

In questo esempio verranno create le [configurazioni](general-electronic-reporting.md#Configuration) ER necessarie per la società di esempio **Litware, Inc**. Verifica che il provider di configurazione per la società di esempio **Litware, Inc.** (`http://www.litware.com`) sia elencato per il framework ER e sia contrassegnato come **Attivo**. Se questo provider di configurazione non è elencato o non è contrassegnato come **Attivo**, completare i passaggi in [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Immetti una nuova fattura a testo libero

1. Segui i passaggi in [Creare una fattura a testo libero](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) per aggiungere una fattura a testo libero.

    1. Aggiungi una riga singola alla fattura.
    2. Aggiungi cinque note per la riga della fattura.

    ![Revisione delle note di riga della fattura nella pagina Allegati.](./media/er-keep-excel-rows-together-notes.png)

2. Segui i passaggi in [Copiare righe](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) per creare cinque righe di fattura aggiuntive che sono copie della riga di fattura aggiunta nel passaggio precedente.

    ![Revisione delle righe della fattura a testo libero nella pagina Fattura a testo libero.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per progettare una versione personalizzata di un formato ER standard.

## <a name="import-the-standard-er-format-configuration"></a>Importare la configurazione del formato ER standard

Segui i passaggi in [Importare la configurazione del formato ER standard](er-quick-start2-customize-report.md#ImportERSolution1) per aggiungere le configurazioni ER standard alla tua attuale istanza di Dynamics 365 Finance. Ad esempio, la versione di importazione **252.116** della configurazione del formato **Fattura a testo libero (Excel)**. La versione base **252** della configurazione **Modello fattura** di base viene importata automaticamente dal repository insieme alla configurazione **Mapping modello di fattura** obbligatoria.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Configurare la gestione della stampa per utilizzare il formato ER standard

Segui i passaggi in [Configurare la gestione della stampa](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1) per configurare la gestione della stampa per il modulo **Contabilità clienti** in modo che il formato ER standard venga utilizzato per stampare fatture a testo libero.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Configurare una destinazione di formato per il formato ER standard

Segui i passaggi in [Configurare una destinazione di formato per l'anteprima su schermo](er-quick-start1-new-solution.md#ConfigureDestination) per configurare la destinazione ER [Schermata](er-destination-type-screen.md) del formato ER standard in modo che i report generati vengano convertiti in formato PDF e visualizzati in anteprima in una nuova scheda del browser.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Stampare una fattura a testo libero utilizzando il formato ER standard

1. Segui i passaggi in [Stampare una fattura a testo libero](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) per utilizzare il formato ER standard per generare un report fattura a testo libero in formato Excel per la fattura aggiunta.
2. Scarica la cartella di lavoro di Excel generata ed esaminala nell'applicazione desktop Excel.

    Tieni presente che la sesta riga della fattura inizia nella prima pagina del report e continua nella seconda pagina. L'ultima nota appare nella seconda pagina e non è ovvio che appartenga alla sesta riga della fattura. Pertanto, l'interruzione di pagina nel mezzo del contenuto della riga della fattura rende questo documento più difficile da leggere.

    ![Revisione dell'impaginazione della fattura a testo libero generata nell'applicazione desktop Excel.](./media/er-keep-excel-rows-together-invoice1.gif)

Le restanti procedure in questo articolo mostrano come ottimizzare il formato ER standard per migliorare l'aspetto e la leggibilità del report fattura mantenendo tutto il contenuto di una singola riga di fattura nella stessa pagina.

## <a name="create-a-custom-format"></a>Creare un formato personalizzato

Segui i passaggi in [Creare un formato personalizzato](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) per derivare un formato dal formato ER importato e creare una configurazione ER **Fattura a testo libero (Excel) personalizzata** disponibile per la modifica.

## <a name="edit-the-custom-format"></a>Modificare il formato personalizzato

1. Segui i passaggi in [Creare un formato personalizzato](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) per aprire il formato ER derivato per la modifica nella progettazione del formato ER.
2. Nella pagina **Progettazione formati**, nell'albero dei componenti dei formati nel riquadro sinistro, espandi **Fattura a testo libero \> Foglio \> InvoiceLines** e seleziona il componente **InvoiceLines_Values**.
3. Nella scheda **Formato**, imposta l'opzione **Mantieni righe insieme** su **Sì**.

    ![Impostazione dell'opzione Mantieni righe insieme per il formato ER modificabile nella pagina Progettazione formato.](./media/er-keep-excel-rows-together-format.png)

4. Selezionare **Salva**, quindi chiudere la pagina.

## <a name="mark-the-custom-format-as-runnable"></a>Contrassegnare il formato personalizzato come eseguibile

Segui i passaggi in [Contrassegnare il formato personalizzato come eseguibile](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) per rendere eseguibile la versione modificata del formato ER personalizzato.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Configurare la gestione della stampa per utilizzare il formato ER personalizzato

Segui i passaggi in [Configurare la gestione della stampa](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2) per configurare la gestione della stampa per il modulo **Contabilità clienti** in modo che il formato ER personalizzato venga utilizzato per stampare fatture a testo libero.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Configurare una destinazione di formato per il formato ER personalizzato

Segui i passaggi in [Configurare una destinazione di formato per l'anteprima su schermo](er-quick-start1-new-solution.md#ConfigureDestination) per configurare la destinazione ER **Schermata** del formato ER personalizzato in modo che i report generati vengano convertiti in formato PDF e visualizzati in anteprima in una nuova scheda del browser.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Stampare una fattura a testo libero utilizzando il formato ER personalizzato

1. Segui i passaggi in [Stampare una fattura a testo libero](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) per utilizzare il formato ER personalizzato per generare un report fattura a testo libero in formato Excel per la fattura aggiunta.
2. Scarica la cartella di lavoro di Excel generata ed esaminala nell'applicazione desktop Excel.

    Si noti che la sesta riga della fattura inizia nella seconda pagina e tutte le righe di Excel che rappresentano questa riga della fattura vengono visualizzate insieme in quella pagina.

    ![Revisione dell'impaginazione aggiornata della fattura a testo libero generata nell'applicazione desktop Excel.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

[Progettare una configurazione per generare documenti in uscita in formato Excel](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
