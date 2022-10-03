---
title: Risoluzione dei problemi di configurazione di Finance Insights
description: Questo articolo elenca i problemi che possono verificarsi quando si utilizzano le funzionalità di Finance Insights. Spiega anche come risolvere questi problemi.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 331c714663d212471b72f1558e6183452ef7f394
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573174"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Risoluzione dei problemi di configurazione di Finance Insights

[!include [banner](../includes/banner.md)]

Questo articolo elenca i problemi che possono verificarsi quando si utilizzano le funzionalità di Finance Insights. Spiega anche come risolvere questi problemi.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Sintomo: perché non riesco a mappare la colonna di destinazione del modello di integrazione dei dati Informazioni dettagliate pagamenti cliente?

### <a name="resolution"></a>Risoluzione

È possibile che si stia utilizzando un modello per una versione precedente. Prima del rilascio della versione 10.0.17, i clienti dell'anteprima configuravano il modello di integrazione dei dati (DI) **Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)** utilizzando l'entità **Risultato della previsione di pagamento (anteprima)**. Dopo un aggiornamento alla versione 10.0.17 e successive, è necessario utilizzare il modello DI **Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17 e versioni successive)** per completare il mapping. Potrebbe non essere possibile mappare la colonna di destinazione del modello DI finché l'elenco delle entità di gestione dei dati non viene aggiornato e l'entità **Risultato della previsione di pagamento** non appare in esso. Per aggiornare l'elenco delle entità e mostrare il risultato della previsione di pagamento, è necessario completare i passaggi in Microsoft Dynamics 365 Finance e Dataverse (precedentemente denominato portale di amministrazione Common Data Service \[CDS\]).

### <a name="in-finance"></a>In Finance

In Finance, dopo l'aggiornamento, eseguire i passaggi indicati di seguito.

1. Passare all'**Amministrazione sistema \> Aree di lavoro \> Gestione dati**.
2. Nell'area di lavoro **Gestione dati**, selezionare il riquadro **Parametri del framework**.
3. Nella pagina **Parametri framework di importazione/esportazione dei dati**, selezionare **Impostazioni entità**, quindi **Aggiorna elenco entità**.
4. Chiudere la pagina **Parametri framework di importazione/esportazione dei dati**.
5. Nell'area di lavoro **Gestione dati** selezionare la scheda **Entità di dati**.
6. Cercare "Risultato della previsione di pagamento". Verificare che l'entità **Risultato della previsione di pagamento** non sia la versione di anteprima. Il nome della versione di anteprima termina con "(anteprima)". Se è visibile solo la versione di anteprima dell'entità, contattare il supporto tecnico Microsoft.

### <a name="in-dataverse"></a>In Dataverse

Seguire questi passaggi nell'[interfaccia di amministrazione Power Platform](https://admin.powerplatform.microsoft.com/environments) per aggiornare i progetti di integrazione dei dati.

1. Se si sta utilizzando una versione di anteprima di Finance Insights, rimuovere il progetto DI associato al modello **Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)**.
2. Seguire i passaggi in [Creare un progetto di integrazione dei dati](create-data-integrate-project.md). Utilizzare il modello **Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17 e versioni successive)**.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Sintomo: quando provo ad aprire AI Builder utilizzando i collegamenti nella pagina di configurazione delle previsioni di pagamento del cliente, perché ricevo il seguente messaggio di errore: "Siamo spiacenti, si è verificata una disconnessione"?

### <a name="resolution"></a>Risoluzione

Gli utenti di Dynamics 365 Finance devono avere un account utente di Microsoft Power Apps per l'ambiente e tale account utente deve avere il ruolo di Addetto alla personalizzazione del sistema. L'amministratore di sistema di Microsoft Power Apps può creare l'account utente e assegnare il ruolo. Puoi quindi andare su <https://make.preview.powerapps.com/>, accedere utilizzando quell'account utente e riprovare i collegamenti.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Sintomo: perché la scheda Previsione di cassa nell'area di lavoro Previsione di cassa non mostra alcun dato?

### <a name="resolution"></a>Risoluzione

La funzione di previsione di cassa in Gestione cassa e banche e la funzione Previsioni di cassa in Finance Insights devono essere configurate e abilitate per mostrare correttamente i dati nell'area di lavoro **Previsione di cassa**.

Innanzitutto, configurare e abilitare i conti liquidità e la previsione di cassa. Per ulteriori informazioni, vedi [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md). Se questa configurazione è stata completata ma non sono visibili i risultati previsti, vedere [Risolvere i problemi di configurazione della previsione del flusso di cassa](../cash-bank-management/cash-flow-forecasting-tsg.md) per maggiori informazioni.

Quindi, confermare che la funzione Previsioni di cassa in Finance Insights (**Gestione cassa e banca \> Impostazioni \> Finance Insights \> Previsioni di cassa**) sia stata abilitato e che il training del modello di intelligenza artificiale sia stato completato. Se il training non è stato completato, selezionare **Esegui previsione ora** per avviare il processo di training del modello.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Sintomo: perché il pulsante Installa un nuovo componente aggiuntivo non è visibile in Microsoft Dynamics Lifecycle Services?

### <a name="resolution"></a>Risoluzione

Innanzitutto, verifica che il ruolo **Responsabile ambiente** o **Proprietario del progetto** sia assegnato all'utente che ha eseguito l'accesso nel campo **Ruolo di sicurezza del progetto** in Microsoft Dynamics Lifecycle Services (LCS). L'installazione dei nuovi componenti aggiuntivi richiede uno di questi ruoli di sicurezza del progetto.

Se ti è stato assegnato il ruolo di sicurezza del progetto corretto, potresti dover aggiornare la finestra del browser per vedere il pulsante **Installa nuovo componente aggiuntivo**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Sintomo: il componente aggiuntivo Finance insights non sembra essere installato. Perché?

### <a name="resolution"></a>Risoluzione

I seguenti passaggi devono essere stati completati.

- Verifica di avere l'accesso di **Amministratore di sistema** e **Responsabile della personalizzazione del sistema** all'interfaccia di amministrazione di Power Portal.
- Verifica che una licenza Dynamics 365 Finance o equivalente sia applicata all'utente che sta installando il componente aggiuntivo.
- Verifica che la seguente app Azure AD sia registrata in Azure AD: 

    | Domanda di lavoro                  | ID app           |
    | ---------------------------- | ---------------- |
    | CDS microservizi ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
    Per verificare che l'applicazione sia registrata in Azure AD, controlla l'elenco **Tutte le applicazioni**. Per maggiori dettagli, vedi [Visualizzare le applicazioni aziendali](/azure/active-directory/manage-apps/view-applications-portal).
  
    Se l'applicazione non è registrata in Azure AD, contatta il supporto.

## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Sintomo: errore, "Non abbiamo trovato alcun dato per l'intervallo di filtri selezionato. Seleziona un intervallo di filtri diverso e riprova." 

### <a name="resolution"></a>Risoluzione

Controlla la configurazione dell'integratore di dati per verificare che funzioni come previsto e che stia aggiornando i dati da AI Builder a Finance.  
Per altre informazioni, vedi [Creare un progetto di integrazione dei dati](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Sintomo: il training di previsione dei pagamenti del cliente non è riuscito e l'errore di AI Builder è: "La previsione dovrebbe avere solo 2 valori di risultato distinti per il training del modello. Esegui il mapping a due risultati ed effettua nuovamente il training", "Errore report di training: IsNotMinRequiredDistinctNonNullValues".

### <a name="resolution"></a>Risoluzione

Questo errore indica che non ci sono abbastanza transazioni storiche nell'ultimo anno che rappresentano ciascuna categoria descritta nelle categorie **Puntuale**, **In ritardo** e **Molto in ritardo**. Per risolvere questo errore, regola il periodo di transazione **Molto tardi**. Se la regolazione del periodo di transazione **Molto tardi** non risolve l'errore, **Previsioni di pagamento dei clienti** non è la soluzione migliore da utilizzare in quanto necessita di dati in ciascuna categoria per scopi di training.

Per ulteriori informazioni su come regolare le categorie **Puntuale**, **In ritardo**, e **Molto in ritardo**, vedi [Abilitare le previsioni di pagamento dei clienti](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Sintomo: il training del modello non è riuscito

### <a name="resolution"></a>Risoluzione

Il training del modello **Previsione di cassa** richiede dati che coprono più di un anno e contengono 100 o più transazioni. Consigliamo di avere almeno due anni di dati con più di 1.000 transazioni.

La funzionalità **Previsioni di pagamento del cliente** richiede più di 100 transazioni nei sei-nove mesi precedenti. Le transazioni possono includere fatture a testo libero, ordini cliente e pagamenti dei clienti. Questi dati devono essere estesi alle impostazioni **Puntuale**, **In ritardo** e **Molto in ritardo** definite nella pagina **Configurazione**.    

La funzionalità **Proposta di budget** richiede un minimo di tre anni di budget o dati effettivi. Questa soluzione utilizza da tre a dieci anni di dati nelle proiezioni. Più di tre anni di dati forniscono risultati migliori. I dati stessi funzionano meglio quando c'è variazione nei valori. Se i dati contengono tutti i dati costanti, come una spesa di locazione, la formazione potrebbe non riuscire perché la mancanza di variazione non richiede all'IA di proiettare gli importi.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Sintomo: il messaggio di errore indica che la "Tabella con nome, 'msdyn_paypredpredictionresultentities' non esiste. Il server remoto ha restituito un errore: (404) Non trovato..."

### <a name="resolution"></a>Risoluzione

L'ambiente ha raggiunto il limite massimo di tabelle di Data Lake Services. Per ulteriori informazioni sul limite, vedi la sezione **Abilita modifiche ai dati near real-time** dell'articolo [Panoramica di Esporta in Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
