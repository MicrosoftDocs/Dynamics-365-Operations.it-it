---
title: Configurare le destinazioni ER specifiche per la gestione della stampa
description: Questo argomento spiega come configurare le destinazioni specifiche dei record di gestione della stampa per un formato di reporting elettronico (ER) che è configurato per generare documenti in uscita.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4cd99b1d2c0dbbf48e7eee7e1233e3b078d14ba3
ms.sourcegitcommit: 6109fc2fe5f407363bb6f240d64b7214657f5914
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2022
ms.locfileid: "8603056"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Configurare le destinazioni ER specifiche per la gestione della stampa

[!include [banner](../includes/banner.md)]

Questo argomento spiega come un utente con il ruolo di amministratore di sistema o di impiegato contabile può eseguire i seguenti compiti:

- Configurare le destinazioni denominate [Electronic reporting (ER)](general-electronic-reporting.md) per una soluzione ER che genera fatture a testo libero.
- Assegna una destinazione ER a un singolo record di [gestione della stampa](document-reporting-services.md) .

Le procedure possono essere completate nell'azienda USMF. Non è richiesta alcuna codifica.

## <a name="introduction"></a>Introduzione

È possibile configurare le [destinazioni](electronic-reporting-destinations.md) per ogni cartella nel componente di output dei file di una[configurazione del](general-electronic-reporting.md#Configuration)  [formato](general-electronic-reporting.md) ER che viene utilizzato per generare un documento in uscita. Quando si esegue un formato ER di questo tipo, se si hanno i diritti di accesso appropriati, si possono anche cambiare le impostazioni di destinazione configurate in fase di esecuzione.

In Microsoft Dynamics 365 Finance **versione 10.0.17 e successive**, un codice di azione può essere [impostato](er-apis-app10-0-17.md) per un formato ER per specificare l'azione che gli utenti eseguono eseguendo quel formato ER. Per esempio, nel modulo **Contabilità clienti** , nelle impostazioni di gestione della stampa, è possibile selezionare un formato ER che genera un documento commerciale specifico, come una fattura a testo libero. È quindi possibile selezionare **Visualizza** per visualizzare in anteprima la fattura o **Stampa** per inviarla a una stampante. Se un'azione viene passata per il formato ER in esecuzione a runtime, è possibile [configurare diverse destinazioni ER per diverse azioni utente](er-action-dependent-destinations.md).

In Finance **versione 10.0.21 e successive**, una destinazione nominata può essere [impostata](er-apis-app10-0-21.md) per un formato ER e assegnata al record di gestione della stampa che viene elaborato quando quel formato ER viene eseguito. Per esempio, nel modulo **Contabilità clienti** , nelle impostazioni di gestione della stampa, volete configurare il record **originale** per eseguire le seguenti azioni:

- Eseguire un formato ER.
- Invia via e-mail la fattura generata a un cliente.
- Configura il record di **copia** per eseguire lo stesso formato.
- Stampa una copia della fattura su una stampante di rete.

In questo caso, dovete configurare diverse destinazioni ER per il formato ER in esecuzione, e dovete selezionare le destinazioni per diversi record di gestione della stampa.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, la funzione **Consenti di impostare le destinazioni ER per elemento di gestione della stampa** deve essere attivata nell'area di lavoro [Gestione funzioni](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) . Il codice sorgente deve anche essere cambiato per permettere la configurazione di destinazioni ER nominate nell'istanza Finance corrente e per abilitare la [nuova](er-apis-app10-0-21.md) ER API.

Inoltre, la configurazione **Fattura a testo libero (Excel)** ER deve essere [importata](er-download-configurations-global-repo.md) nella tua istanza Finance.

## <a name="configure-a-new-er-destination"></a>Configurare una nuova destinazione ER

1. Passare a **Contabilità clienti** \> **Fatture** \> **Tutte le fatture a testo libero**.
2. Seleziona una fattura per il conto cliente **US-001**.
3. Nella pagina della **fattura a testo libero** , nella scheda **Fattura** , nel gruppo **Gestione della stampa** , seleziona **Gestione della stampa**.
4. Nella pagina **di impostazione della gestione di stampa** , espandere **Modulo - contabilità clienti** \> **Documenti** \> **Fattura a testo libero**, selezionare il record **Originale** , e poi seguire questi passi:

    1.  Osserva le impostazioni attuali del record selezionato:
        -   Il rapporto predefinito SSRS **FreeTextInvoice.Report** è selezionato nel campo **Formato report** .
        -   Il **\<Default\>** viene mostrato nel campo **Destinazione** informando che non c'è una destinazione personalizzata selezionata per il rapporto SSRS assegnato. 
    2.  Nel campo **Formato rapporto** , seleziona la configurazione del formato **Fattura a testo libero (Excel)** ER.
        -   Il nome del campo **Destinazione** viene cambiato in **Nome destinazione**.
        -   Il **\<No named destination\>** viene mostrato nel campo **Nome destinazione** informando che non c'è una destinazione nominata selezionata per il formato ER assegnato.
    3.  Seleziona il pulsante con la freccia a destra del campo **Nome della destinazione** .    
    4. Nella pagina **Destinazione denominata report elettronici** , nel campo **Nome** , inserite **Destinazione principale**.
    5. Selezionare **Salva**.
    6. Sulla FastTab **Destinazione file** , [configura](er-destination-type-email.md) la destinazione **E-mail** per il componente **Report** .
    7. Chiudere la pagina di **destinazione Electronic reporting named** .
    8. Nella pagina **di impostazione della gestione di stampa** , nel campo **Nome della** destinazione, selezionate la **destinazione principale** denominata destinazione.

    ![Configurare una destinazione ER nominata per il formato ER selezionato e assegnarla a un record di gestione della stampa configurato nella pagina di impostazione della gestione della stampa](./media/er-named-destinations-01.gif)

    Avete ora configurato la destinazione ER denominata **Destinazione principale** per il formato **Fattura a testo libero (Excel)** e l'avete assegnata al record di gestione della stampa **originale** in **Modulo - contabilità clienti** \> **Documenti** \> **Fattura a testo libero**.

5. Espandere **Modulo - contabilità clienti** \> **Account - US-001** \> **Fattura a testo libero**, selezionare il record **originale** e poi seguire questi passi:

    1. Selezionate e tenete premuto (o cliccate con il tasto destro del mouse) il record, quindi selezionate **Sostituisci**.
    2. Seleziona il pulsante con la freccia a destra del campo **Nome della destinazione** .
    3. Nella pagina di **destinazione denominata Electronic reporting** , nel riquadro Azione, seleziona **Nuovo**.
    4. Nel campo **Nome** , inserite la **destinazione US-001**.
    5. Sulla FastTab **Destinazione file** , [configura](er-destination-type-print.md) la destinazione **stampante** per il componente **Report** .
    6. Chiudere la pagina di **destinazione Electronic reporting named** .
    7. Nella pagina **di impostazione della gestione della stampa** , nel campo **Nome della** destinazione, selezionare la **destinazione US-001** denominata destinazione.

    ![Configurare una destinazione ER nominata per il formato ER selezionato e assegnarla al record di gestione della stampa configurato nella pagina di impostazione della gestione della stampa](./media/er-named-destinations-02.gif)

    Avete ora configurato la destinazione ER denominata **US-001** per il formato di **fattura a testo libero (Excel)** e l'avete assegnata al record di gestione della stampa **originale** in **Modulo - contabilità clienti** \> **Conto - US-001** \> **Fattura a testo libero**.

Ora, quando una fattura a testo libero viene elaborata, viene eseguito il formato **Fattura a testo libero (Excel)** ER, e si verifica uno dei seguenti eventi:

- Se la fattura a testo libero è per un cliente diverso da US-001, il documento generato viene inviato via e-mail.
- Se la fattura a testo libero è per il cliente US-001, il documento generato viene stampato.

> [!NOTE]
> Quando una destinazione nominata non è stata definita per un record di gestione della stampa che viene elaborato in fase di esecuzione, le destinazioni ER predefinite vengono utilizzate se sono disponibili per il formato ER in esecuzione.

> [!IMPORTANT]
> Nella pagina della **destinazione di reporting elettronico** **(Amministrazione dell'organizzazione** \> **Reporting elettronico** \> **Destinazione di reporting elettronico**), se si seleziona un formato ER per il quale è stata configurata almeno una destinazione nominata, si riceve una notifica sulla presenza di destinazioni nominate.
>
> ![Notifica dell'esistenza di destinazioni nominate configurate per il formato ER selezionato nella pagina Destinazione di segnalazione elettronica](./media/er-named-destinations-03.png)
>
> Se si elimina la destinazione predefinita, vengono eliminate anche tutte le destinazioni nominate. Se queste destinazioni nominate sono state selezionate per i record di gestione della stampa, la selezione di queste destinazioni nominate viene annullata.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Copiare una destinazione ER esistente come una nuova destinazione con nome

Quando la destinazione ER con nome predefinito è disponibile per un formato ER, può essere usata come modello per nuove destinazioni ER. Per creare una nuova destinazione ER basata sulla destinazione predefinita, selezionare **Copia da predefinito** nella pagina **Destinazione denominata report elettronici** . La nuova destinazione si chiama **Predefinito**. Potete ripetere questo passo tutte le volte che volete.

Si può selezionare qualsiasi destinazione nominata esistente come modello per una nuova destinazione nominata. Per creare una nuova destinazione ER nominata che si basa su una destinazione nominata selezionata, selezionare **Copia** nella pagina **Destinazione denominata report elettronici** . La nuova destinazione ha lo stesso nome della destinazione selezionata, ma viene aggiunto il suffisso "Copia". Potete ripetere questo passo tutte le volte che volete.

## <a name="security-considerations"></a>Considerazioni sulla sicurezza

È possibile impostare le destinazioni ER nominate nella pagina **di impostazione della gestione della stampa** solo se si ha il [permesso](../sysadmin/role-based-security.md#permissions) di eseguire questa attività. L'autorizzazione ti può essere concessa se il [compito](../sysadmin/role-based-security.md#duties)  **Configura la destinazione del formato di segnalazione elettronica** è assegnato a uno dei tuoi [ruoli di sicurezza](../sysadmin/role-based-security.md#security-roles). Per maggiori informazioni, vedere [Considerazioni sulla sicurezza](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della creazione di report elettronici](general-electronic-reporting.md)

[Destinazioni dei report elettronici](electronic-reporting-destinations.md)

[Modifiche dell'API framework di report elettronici per Application update 10.0.17](er-apis-app10-0-17.md)

[Modifiche dell'API framework di report elettronici per Application update 10.0.21](er-apis-app10-0-21.md)

[Modificare il codice per permettere agli utenti di configurare e utilizzare le destinazioni ER nominate](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
