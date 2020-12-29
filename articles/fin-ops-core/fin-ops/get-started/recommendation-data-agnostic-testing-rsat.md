---
title: Test agnostico dei dati utilizzando Regression Suite Automation Tool
description: In questo argomento vengono forniti suggerimenti per il test agnostico dei dati utilizzando Regression Suite Automation Tool.
author: kfend
manager: AnnBe
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 7fd1fc4756e74a5d07ffae533b6b9837b960f17a
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693752"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Test agnostico dei dati utilizzando Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Sebbene la convalida funzionale di un'applicazione ERP non possa essere completamente indipendente dai dati, ci sono più fasi e approcci per i test. Queste fasi di test sono:  

- Framework SysTest
- Framework ATL
- Regression Suite Automation Tool (RSAT)

[![Piramide di classificazione test](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Panoramica
-   **Framework SysTest** - Il framework SysTest è attendibile per la scrittura degli unit test. Poiché gli unit test in genere verificano un metodo o una funzione, devono sempre essere agnostici dai dati e dipendenti solo dai dati di input specificati come parte del test.
-   **Framework ATL** - Microsoft ha un framework ATL che è un'astrazione nel framework SysTest ed effettua un test funzionale di scrittura molto più semplice e affidabile. Il framework deve essere utilizzato per la scrittura dei test componenti o test di integrazione semplici.
-   **RSAT** - Lo strumento RSAT viene utilizzato per i test di integrazione e i test del ciclo aziendale. I test del ciclo aziendale, anche denominati test di convalida regressione, dipendono dai dati esistenti. Tuttavia, i test possono diventare agnostici dai dati se vengono considerati fattori aggiuntivi. 

    - o Laddove gli unit test e i test componenti sono di basso livello e possono essere completamente indipendenti dai dati (non dipendenti dal set di dati esistente), i test di convalida del ciclo aziendale o della regressione dipendono da alcuni dati esistenti. Questi dati inclusono l'impostazione, le impostazioni di configurazione (parametri) e i dati master (clienti, fornitori, articoli e così via.), ma non i dati della transazione. Se uno di questi dati vengono modificati durante un test, assicurarsi che vengano reimpostati come parte del test finale.
    - Selezionare i dati master in base a determinati criteri anziché selezionare un record specifico. Ad esempio, se si desidera selezionare un articolo in base ai valori di dimensione e alla disponibilità delle scorte, filtrate l'elenco dei prodotti con tali valori, selezionare il primo articolo e copiare il numero da utilizzare per i test futuri. Se è una riga di dati master semplice ad esempio cliente, fornitore o articolo, può essere creata come parte dell'automazione e utilizzata in test futuri tramite concatenamento. 
    - o Immettere gli identificatori univoci, come i numeri di fattura, tramite la sequenza numerica o utilizzando le funzioni di Microsoft Excel come =TEXT(NOW(),"yyyymmddhhmm"). Questa funzione fornirà un numero univoco ogni minuto, che consente di tenere traccia dell'azione eseguita. Può essere usata per le variabili come i numeri di ricevuta del prodotto e i numeri di fattura del fornitore. Questi test continuano a funzionare sullo stesso database, senza richiedere alcun ripristino.
    - Impostare sempre la **modalità di modifica** dell'ambiente su **Lettura** o **Modifica** come primo test case perché l'opzione predefinita è **Automatico**. L'opzione **Automatico** utilizza sempre l'impostazione precedente e può causare test inaffidabili. 
 
    [![Pagina Opzioni, scheda Prestazioni](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Convalidare solo dopo aver filtrato una determinata transazione anziché effettuare una convalida generica. Ad esempio, per il numero di record, filtrare per il numero di transazione o la data della transazione in modo che la convalida escluda tutte le altre transazioni. 
    - Se si sta verificando un saldo del cliente o un controllo del budget, salvare prima il valore e quindi aggiungere il valore della transazione per convalidare il risultato previsto anziché un valore previsto fisso. 
 
