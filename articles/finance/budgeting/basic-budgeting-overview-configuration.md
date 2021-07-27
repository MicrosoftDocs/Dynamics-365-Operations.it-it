---
title: Panoramica di Impostazione budget
description: Quasi tutte le società che utilizzano la funzionalità Dati finanziari in Microsoft Dynamics 365 Finance devono poter creare report di confronto tra budget e valori effettivi. In questo articolo viene descritta la configurazione minima richiesta per creare budget in Finance and Operations o per caricarli da un programma di terze parti.
author: panolte
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60113"
- intro-internal
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f79da43fa89fd98b3079dc69614553e74493376
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338784"
---
# <a name="budgeting-overview"></a>Panoramica dell'impostazione budget 

[!include [banner](../includes/banner.md)]

Quasi tutte le società che utilizzano la funzionalità Dati finanziari in Microsoft Dynamics 365 Finance devono poter creare report di confronto tra budget e valori effettivi. In questo articolo viene descritta la configurazione minima richiesta per creare budget in Finance and Operations o per caricarli da un programma di terze parti.

## <a name="overview"></a>Panoramica

Il budget approvato per una persona giuridica viene gestito in un documento noto come *voce del registro di budget*. Le righe di un documento di voci di registro del budget sono note come voci *contabili del budget* e contengono le informazioni sulle dimensioni finanziarie, le date e gli importi del budget approvato. Il documento delle voci del registro di budget è integrato con i report finanziari di base e le pagine di richiesta di informazioni in cui gli importi effettivi di contabilità generale vengono confrontati gli importi del budget. 

Esistono più metodi per creare voci del registro di budget:

-   Immettere manualmente le informazioni del documento nella pagina **Voci del registro di budget**.
-   Utilizzare il modello di Microsoft Excel che è possibile aprire facendo clic sul pulsante **Apri in Excel** nella pagina **Voci del registro di budget**.
-   Utilizzare l'entità di dati **Voci contabili del budget** in Gestione dati per importate le voci del registro di budget. Può essere utile utilizzare questo metodo e attivare il parametro **Elaborazione basata su set** quando occorre importare nel sistema numerose voci contabili del budget.
-   Se la società utilizza la funzionalità di pianificazione del budget per preparare i dati del budget, è possibile utilizzare il processo periodico **Genera voce del registro di budget**.

La voce del registro di budget viene considerata completata dopo che i saldi budget sono stati aggiornati. Nella pagina **Voci del registro di budget** fare clic su **Aggiorna saldi budget** per una voce del registro di budget selezionata o per più voci. Dopo aver aggiornato i saldi budget, lo stato della voce del registro di budget viene impostato su **Completata**. La voce del registro di budget completata non può essere aperta nuovamente per eventuali modifiche. Di conseguenza, se i dati del budget devono essere rettificati, è necessario creare una nuova voce del registro di budget invece di correggere i dati della voce del registro di budget completata.

## <a name="configuration"></a>Configurazione
Per configurare l'impostazione del budget, iniziare dalla pagina **Parametri impostazione budget**. In questa pagina, è necessario definire il giornale di registrazione budget, la sequenza numerica per le voci del registro di budget e il comportamento predefinito nelle aree di lavoro.

Successivamente, se esistono criteri che regolano l'approvazione delle voci del registro di budget, in base al tipo di budget (ad esempio, trasferimenti o revisioni), è necessario creare flussi di lavoro delle voci del registro di budget nella pagina **Flussi di lavoro impostazione budget**. Se sono presenti scenari in cui i trasferimenti possono essere consentiti senza l'approvazione del flusso di lavoro, è possibile definire le regole di trasferimento budget per supportare tali scenari. 

Nella pagina **Dimensioni impostazione budget** è necessario selezionare le dimensioni finanziarie che vengono utilizzate per l'impostazione del budget, in base alle dimensioni che vengono utilizzate nel piano dei conti. Per l'impostazione del budget è possibile selezionare tutte le dimensioni finanziarie o un sottoinsieme di esse.

Definire un *modello di budget* che corrisponda a tutti o ad alcuni dei budget. È possibile utilizzare un unico modello di budget per tutte le voci del registro di budget. In alternativa, è possibile creare modelli separati basati sul tipo di budget, la posizione geografica o un altro modo in cui un budget può essere classificato. 

> [!NOTE] 
> Se viene utilizzato il controllo del budget, è possibile associare un solo modello di budget a una durata ciclo di budget specifica. 

Creare *codici budget* che identificano il tipo di transazioni budget da registrare e i flussi di lavoro correlati. I codici budget possono supportare i seguenti tipi di budget:

-   Budget originale
-   Trasferito
-   Revisione
-   Impegno di spesa
-   Impegno preliminare di spesa
-   Budget riportabile in avanti

I codici budget consentono di avere una audit trail di modifiche di budget approvate nel corso del ciclo del budget. Se un flusso di lavoro è associato a un codice budget, il flusso di lavoro verrà attivato per tutte le voci del registro di budget che utilizzano tale codice budget e i passaggi del flusso di lavoro dovranno essere completati prima che la voce del registro di budget possa raggiungere lo stadio **Completata**.  

È inoltre possibile impostare delle *regole di trasferimento budget*. Per utilizzare le regole di trasferimento budget, selezionare **Usa regole per trasferimenti di budget** nella pagina **Parametri budget**. Quando si utilizzano le regole per trasferimenti di budget, se un utente crea un documento utilizzando un codice budget del tipo **Trasferimento**, i saldi budget non verranno aggiornati se tali regole vengono violate. Ad esempio, è possibile consentire documenti di trasferimento budget dove il budget di spesa viene trasferito tra i conti principali del reparto Vendite e marketing, ma è possibile impedire il trasferimento del budget da o verso quel reparto a meno che non sia stata concessa l'approvazione del flusso di lavoro per quel tipo di voce contabile del budget.

La funzionalità che è stata introdotta in Microsoft Dynamics 365 Finance versione 10.0.7 (gennaio 2020) è stata integrata con la capacità e la flessibilità per le voci del registro di budget. Per consentire questi miglioramenti, passare all'area di lavoro **Gestione della funzionalità** e selezionare **Solo voci del registro di budget della quantità** e/o **Voci del registro di budget predefinite per tipo di importo**.

La funzionalità **Solo voci del registro della quantità** consente di registrare una voce del registro di budget con gli importi solo per quantità. Ad esempio, è possibile registrare una voce del budget con una quantità pari a 32 e un prezzo pari a zero, che determina un importo pari a zero. È quindi possibile utilizzare la quantità nel contesto di un report finanziario per determinare il prezzo per quantità. Tenere presente che le richieste di informazioni o i report non sono stati aggiornati come parte di questa funzionalità; la funzionalità consente di registrare per un importo pari a zero.

Con la funzionalità **Voci del registro di budget predefinite per tipo di importo**, il tipo predefinito dell'importo in una voce del registro di budget può essere un tipo di importo diverso spese. La riga della voce del registro di budget ora verrà automaticamente impostata come spesa quando il tipo di conto principale è spesa; verrà automaticamente impostata come ricavi quando il tipo di conto principale è ricavi; e verrà automaticamente impostata come spesa per tutti gli altri tipi di conto.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Utilizzo delle aree di lavoro e delle pagine di richiesta per tenere traccia del budget rispetto valori effettivi
Il responsabile budget può verificare lo stato corrente di un budget nell'area di lavoro **Budget contabili e previsioni**. Le schede relative alle **spese sul budget** e ai **ricavi da budget** offrono una rapida panoramica delle combinazioni delle dimensioni finanziarie dove gli obiettivi del budget non sono stati rispettati o sono vicini alla soglia. È possibile personalizzare la percentuale della soglia del budget e i set di dimensioni finanziarie che sono utilizzati in queste schede facendo clic su **Configura area di lavoro personale**. È possibile fare clic su **Responsabili unità** per vedere i lavoratori che sono responsabili di specifiche combinazioni dimensioni finanziarie che sono selezionate in tali schede. Ad esempio, se si nota che il budget di spesa del reparto Operazioni sta per superare la soglia del budget, è possibile trovare e contattare il responsabile del reparto per discutere del problema. 

> [!NOTE] 
> Il campo **Responsabile reparto** nella pagina **Unità organizzative** determina quali responsabili supportano specifiche combinazioni di dimensioni finanziarie. Fare clic su **Ulteriori informazioni** nella parte inferiore della scheda per aprire la pagina di richiesta **Confronto tra budget e valori effettivi** per visualizzare altri dettagli sugli importi di budget rispetto agli importi effettivi. 

La pagina di richiesta **Effettivi rispetto al budget** consente di esaminare a fondo i dettagli del budget rispetto agli importi effettivi. Selezionare una riga nella pagina di richiesta e quindi fare clic su **Saldi del periodo** per visualizzare come il budget e gli importi effettivi si estendono su più periodi fiscali. La pagina **Voci contabili budget** fornisce informazioni dettagliate sull'importo del budget nelle voci del registro di budget. La pagina **Inserimenti nel giornale di registrazione generale** apre le transazioni contabili che sono incluse nell'importo **Effettivi** calcolato. 

Una società che utilizza la funzionalità di pianificazione del budget può creare e utilizzare le *previsioni di budget* nell'area di lavoro **Budget contabili e previsioni**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
