---
title: Configurare destinazioni ER dipendenti dall'azione
description: Questo articolo spiega come configurare destinazioni dipendenti dall'azione per un formato di Creazione di report elettronici (ER) configurato per generare documenti in uscita.
author: kfend
ms.date: 12/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 80a432a431891c02e4bf5c71cfe2bd9642c41c75
ms.sourcegitcommit: e9000d0716f7fa45175b03477c533a9df2bfe96d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/13/2022
ms.locfileid: "9843799"
---
# <a name="configure-action-dependent-er-destinations"></a>Configurare destinazioni ER dipendenti dall'azione

[!include [banner](../includes/banner.md)]

È possibile configurare [destinazioni](electronic-reporting-destinations.md) per ogni componente di output (cartella o file) di una [configurazione](general-electronic-reporting.md#Configuration) di formato di [Creazione di report elettronici (ER)](general-electronic-reporting.md) utilizzata per generare un documento in uscita. Gli utenti che eseguono un formato ER di questo tipo e che dispongono dei diritti di accesso appropriati possono anche modificare le impostazioni di destinazione configurate in fase di esecuzione.

In Microsoft Dynamics 365 Finance **versione 10.0.17 e successive**, un formato ER può essere eseguito mediante il [provisioning](er-apis-app10-0-17.md) di un codice azione che l'utente mediante quel formato ER. Ad esempio, nel modulo **Contabilità clienti**, nelle impostazioni di gestione della stampa, è possibile selezionare un formato ER che generi un documento aziendale specifico, come una fattura a testo libero. È quindi possibile selezionare **Visualizza** per visualizzare in anteprima la fattura o **Stampa** per inviarla a una stampante. Se un'azione utente viene trasmessa per il formato ER in esecuzione in fase di esecuzione, è possibile configurare diverse destinazioni ER per diverse azioni utente. Questo articolo spiega come configurare le destinazioni ER per questo tipo di formato ER.

## <a name="make-action-dependent-er-destinations-available"></a>Rendere disponibili destinazioni ER dipendenti dall'azione

Per configurare le destinazioni ER dipendenti dall'azione nell'istanza di Finance corrente e abilitare la [nuova](er-apis-app10-0-17.md) API ER, apri l'area di lavoro [Gestione funzionalità](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) e attiva la funzionalità **Configura destinazioni ER specifiche da utilizzare per diverse azioni PM**. Per utilizzare le destinazioni ER configurate per report specifici in fase di esecuzione, abilita la funzionalità **Instrada output dei report Gestione stampa in base alle destinazioni per la creazione di report elettronici specifiche dell'azione utente (ciclo 1)**.

## <a name="configure-action-dependent-er-destinations"></a>Configurare destinazioni ER dipendenti dall'azione

Quando attivi la funzionalità **Configura destinazioni ER specifiche da utilizzare per diverse azioni PM** è possibile configurare destinazioni ER dipendenti dall'azione nella Scheda dettaglio **Destinazione file** della pagina **Destinazione di creazione di report elettronici**. Per ogni componente è possibile aggiungere un record e abilitare destinazioni ER specifiche. Per ogni record, è necessario specificare il tipo di documento per il quale devono essere applicate le destinazioni ER configurate. Nel campo **Tipo documento**, selezionare uno dei seguenti valori:

- Selezionare **Elettronico** per applicare le destinazioni configurate se non viene fornito alcun codice di azione utente in fase di esecuzione.
- Selezionare **Gestione stampa** per applicare le destinazioni configurate se non viene fornito alcun codice di azione utente in fase di esecuzione.
- Selezionare **Qualsiasi** per applicare sempre le destinazioni configurate anche se non viene fornito alcun codice di azione utente in fase di esecuzione.

Se selezioni il tipo di documento **Gestione stampa**, è necessario specificare le azioni utente per le quali devono essere applicate le destinazioni ER configurate. Nel campo **Azione gestione stampa**, selezionare uno dei seguenti valori:

- Selezionare **Visualizza** per applicare le destinazioni configurate se non viene fornita l'azione utente **Visualizza** in fase di esecuzione.
- Selezionare **Stampa** per applicare le destinazioni configurate se non viene fornita l'azione utente **Stampa** in fase di esecuzione.
- Selezionare **Invia** per applicare le destinazioni configurate se non viene fornita l'azione utente **Invia** in fase di esecuzione.

> [!NOTE]
> È possibile selezionare più azioni per un singolo record di destinazione.

Se selezioni il tipo di documento **Qualsiasi**, **Rilevamento automatico** viene selezionato automaticamente nel campo **Azione gestione stampa** come azione dell'utente e si verifica il seguente comportamento:

- Se non viene fornito alcun codice di azione utente in fase di esecuzione, verranno applicate tutte le destinazioni ER configurate.
- Se viene fornito un codice di azione utente in fase di esecuzione, viene applicata una destinazione ER predefinita per un'azione specifica, **indipendentemente dal fatto che sia stato abilitato**:

    - Quando viene fornita l'azione **Visualizza** in fase di esecuzione, viene applicata la destinazione ER **Schermata**.
    - Quando viene fornita l'azione **Invia** in fase di esecuzione, viene applicata la destinazione ER **E-mail**.
    - Quando viene fornita l'azione **Stampa** in fase di esecuzione, viene applicata la destinazione ER **Stampante**.

Ad esempio, puoi utilizzare il formato ER **Fattura a testo libero (Excel)** per stampare una [fattura a testo libero](../../../finance/accounts-receivable/create-free-text-invoice-new.md) quando la pubblichi. Per instradare un documento generato, è necessario configurare le destinazioni ER per questo formato ER. Ad esempio, potrebbe essere necessario configurare queste destinazioni ER per eseguire quanto segue su un documento generato:

- Archivia il documento se viene eseguito il formato ER ma non viene fornito alcun codice di azione (ad esempio, quando il documento viene inviato elettronicamente).
- Visualizza l'anteprima del documento in un browser Web quando un utente esegue l'azione **Visualizza**.
- Archivia e stampa il documento quando un utente esegue l'azione **Stampa**.
- Archivia il documento e invialo tramite posta elettronica come allegato di un messaggio e-mail in uscita quando un utente esegue l'azione **Invia**.

La figura seguente mostra come ottenere questa configurazione delle destinazioni ER come set di record di destinazione individuali quando ogni record è configurato per un'azione di un singolo utente:

![Pagina di destinazione per la creazione di report elettronici con impostazioni di destinazione dipendenti dall'azione per un formato ER quando ogni record di destinazione è configurato per un'azione di un singolo utente.](./media/er-destination-action-dependent-01.png)

La figura seguente mostra come ottenere la stessa configurazione delle destinazioni ER alternativa come set di record di destinazione individuali quando ogni record è configurato per una singola destinazione:

![Pagina di destinazione per la creazione di report elettronici con impostazioni di destinazione dipendenti dall'azione per un formato ER quando ogni record di destinazione è configurato per una singola destinazione.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Se viene fornito un codice azione per il formato ER in esecuzione, ma nessuna destinazione è stata configurata per quel codice azione, viene applicato il comportamento di destinazione [predefinito](electronic-reporting-destinations.md#default-behavior).

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Modificare le destinazioni ER dipendenti dall'azione in fase di esecuzione

Quando viene eseguito un formato ER, se le azioni dell'utente sono state fornite da utenti che dispongono delle [autorizzazioni](electronic-reporting-destinations.md#security-considerations) appropriate per modificare le impostazioni di destinazione configurate in fase di esecuzione, viene visualizzata una finestra di dialogo che offre la possibilità di modificare le impostazioni di destinazione configurate. Questa finestra di dialogo è facoltativa e il suo aspetto dipende da come è stata implementata la chiamata effettuata dal framework ER per eseguire un formato ER. Se viene visualizzata questa finestra di dialogo, le destinazioni ER in essa contenute verranno abilitate in base all'azione dell'utente fornita.

La figura seguente mostra un esempio di finestra di dialogo **Destinazione del formato per la creazione di report elettronici** che appare quando una fattura a testo libero viene [registrata](../../../finance/accounts-receivable/create-free-text-invoice-new.md) e il formato ER **Fattura a testo libero (Excel)** viene eseguito per generare questo documento, se è stato eseguito il provisioning dell'azione **Stampante** e le destinazioni ER sono state configurate per questo formato, come mostrato in precedenza in questo articolo.

![Finestra di dialogo che offre la possibilità di modificare le destinazioni ER configurate inizialmente per il formato ER in esecuzione.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Se sono state configurate destinazioni ER per diversi componenti del formato ER in esecuzione, verrà offerta un'opzione separatamente per ogni componente configurato del formato ER.

Se diversi formati ER sono applicabili come modelli di report per il documento selezionato, tutte le destinazioni ER per tutti i modelli di report ER applicabili vengono visualizzate nella finestra di dialogo e disponibili per la rettifica manuale in fase di esecuzione.

Se al documento selezionato non sono applicabili i modelli di report [SQL Server Reporting Services (SSRS)](SSRS-report.md) , la selezione standard delle destinazioni di gestione della stampa viene nascosta dinamicamente.

A partire dalla versione Finance **10.0.31**, è possibile modificare manualmente le destinazioni ER assegnate in fase di esecuzione per i seguenti documenti commerciali:

- Estratto conto cliente
- Nota d'interesse
- Nota lettera di sollecito
- Avviso di pagamento del cliente
- Avviso di pagamento del fornitore

Per attivare la possibilità di modificare le destinazioni ER in fase di esecuzione, abilita la funzione **Consenti la rettifica delle destinazioni ER in fase di esecuzione** nell'area di lavoro [Gestione funzionalità](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace).

> [!IMPORTANT]
> Per i report **Avviso pagamento cliente** e **Avviso pagamento fornitore** , la possibilità di modificare manualmente le destinazioni ER è disponibile solo se l'anteprima **ForcePrintJobSettings** è abilitata.

[![Rettifica delle destinazioni ER in fase di esecuzione.](./media/ERdestinaiotnChangeUI.jpg)](./media/ERdestinaiotnChangeUI.jpg)

> [!NOTE]
> Quando l'opzione **Usa destinazione gestione stampa** è impostata su **Sì**, il sistema utilizza le destinazioni ER predefinite configurate per specifici report ER. Tutte le modifiche manuali apportate nella finestra di dialogo vengono ignorate. Imposta l'opzione **Usa destinazione gestione stampa** su **No** per elaborare i documenti nelle destinazioni ER definite nella finestra di dialogo immediatamente prima di eseguire i report.

I seguenti documenti commerciali non presuppongono la selezione esplicita dell'utente di un'azione quando vengono eseguiti:

- Estratto conto cliente
- Nota d'interesse
- Nota lettera di sollecito
- Avviso di pagamento del cliente
- Avviso di pagamento del fornitore

La seguente logica viene utilizzata per determinare quale azione viene usata durante l'elaborazione dei report precedenti:

- Se l'anteprima **ForcePrintJobSettings** è abilitata:

    - Se l'opzione **Usa destinazione gestione stampa** è impostata su **Sì**, l'azione **Stampa** viene utilizzata.
    - Se l'opzione **Usa destinazione gestione stampa** è impostata su **No**, l'azione **Visualizza** viene utilizzata.

- Se l'anteprima **ForcePrintJobSettings** non è abilitata:

    - Se l'opzione **Usa destinazione gestione stampa** è impostata su **Sì**, l'azione **Stampa** viene utilizzata per i report **Avviso pagamento cliente** e **Avviso pagamento fornitore**.
    - Se l'opzione **Usa destinazione gestione stampa** è impostata su **No**, il modello di report SSRS predefinito viene sempre utilizzato per i report **Avviso pagamento cliente** e **Avviso pagamento fornitore**, indipendentemente dalle impostazioni ER configurate.
    - L'azione **Stampa** viene sempre utilizzata per i report **Estratto conto cliente**, **Nota interessi**, e **Nota lettera di sollecito**.

Per la logica precedente, le azioni **Stampa** o **Visualizza** possono essere utilizzate per configurare le destinazioni dei report ER dipendenti dall'azione. In fase di esecuzione, nella finestra di dialogo vengono filtrate solo le destinazioni ER configurate per un'azione specifica.

## <a name="verify-the-provided-user-action"></a>Verificare l'azione utente fornita

È possibile verificare quale azione utente, se presente, viene fornita per il formato ER in esecuzione quando si esegue un'azione utente specifica. Questa verifica è importante quando è necessario configurare destinazioni ER dipendenti dall'azione, ma non si è sicuri di quale codice azione utente, se presente, viene fornito. Ad esempio, quando inizi a registrare una fattura a testo libero e imposti l'opzione **Stampa fattura** su **Sì** nella finestra di dialogo **Registra fattura a testo libero**, è possibile impostare l'opzione **Usa destinazione gestione stampa** su **Sì** o **No**.

Attenersi alla seguente procedura per verificare il codice di azione dell'utente fornito.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, [imposta](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) l'opzione **Esegui in modalità di debug** su **Sì**.
4. Esegui un'azione utente mediante l'utilizzo di un formato ER. Tenere presente che il parametro utente ER è specifico dell'utente e dell'azienda.
5. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Registri debug configurazione**.
6. Nella pagina **Registri debug configurazione**, filtra i registri di esecuzione ER per trovare il log per la tua esecuzione in formato ER.
7. Rivedere le voci di registro che devono contenere il record che presenta il codice di azione utente fornito, se è stata fornita un'azione per l'esecuzione del formato ER.

    ![La pagina dei registri di esecuzione della creazione di report elettronici che contiene informazioni sul codice di azione dell'utente fornito per l'esecuzione filtrata di un formato ER.](./media/er-destination-action-dependent-03.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della creazione di report elettronici](general-electronic-reporting.md)

[Destinazioni dei report elettronici](electronic-reporting-destinations.md)

[Modifiche dell'API framework di report elettronici per Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
