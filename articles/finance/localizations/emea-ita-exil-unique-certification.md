---
title: Certificazione Unica
description: Questo articolo fornisce informazioni sulla certificazione unica per le società in Italia.
author: ilkond
ms.date: 03/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 11659daba364882f2168486a0c96a9c1ad35b3cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846506"
---
# <a name="unique-certification"></a>Certificazione unica

[!include [banner](../includes/banner.md)]

In Italia, gli addetti alla ritenuta d'acconto devono comunicare elettronicamente la certificazione unica all'agenzia delle entrate per certificare le seguenti informazioni:

- Reddito di lavoro dipendente
- Reddito autonomo
- Provvigioni
- Altri redditi

## <a name="prerequisites"></a>Prerequisiti

Per poter utilizzare questa funzionalità è necessario soddisfare i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- La funzionalità **Certificazione unica** deve essere attivata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-the-unique-certification"></a>Impostare la certificazione unica

### <a name="set-up-a-number-sequence"></a>Impostare una sequenza numerica

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.
2. Nella scheda **Sequenze numeriche** nella scheda **ID certificazione unica**, definire una sequenza numerica.

### <a name="set-up-the-unique-certification-values"></a>Impostare i valori della certificazione unica

1. Vai a **Imposta** \> **Impostazione** \> **Ritenuta d'acconto** \> **Imposta valori di certificazione univoci**
2. Specifica i valori per la funzionalità **Certificazione unica**.

La pagina **Imposta valori di certificazione univoca** consente di configurare i valori disponibili per diversi campi:

- **Record B**: Eventi eccezionali
- **record D** : eventi eccezionali, categorie speciali e province unificate
- **Record H**: motivo e codice

I valori specificati sulla pagina **Imposta valori di certificazione unica** e contrassegnati con **Sì** nella colonna **Attivo**, saranno disponibili nei relativi campi di ricerca nella pagina **Certificazione unica**. Utilizza questa pagina per futuri aggiornamenti normativi della certificazione unica per aggiungere o eliminare valori.

È possibile importare il set iniziale di valori per **Impostazione valori di certificazione unica** utilizzando l'entità **Impostazione valori certificazione unica** (UniqueCertificationValueEntity) e il framework di gestione dei dati. Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). È possibile scaricare il set iniziale di valori per **Imposta valori di certificazione unica** dal file **IT SetupUniqueCertificationValues** nella sezione del tipo di dati risorsa **Pacchetto dati** della **Libreria di risorse condivisa** nel [Portale LCS](https://lcs.dynamics.com/v2) e quindi importarlo nel framework di gestione dei dati.

I dati di origine utilizzati per l'importazione possono essere presentati come un file di Microsoft Excel con i seguenti nomi di colonna:

- FIELD
- VALORE
- ACTIVE
- VALUEDESCRIPTION

### <a name="set-up-a-revenue-typology-for-the-unique-certification"></a>Impostare una tipologia di entrate per la certificazione unica

È necessario impostare una tipologia di entrate nel campo **Tipologia di entrate** nella sezione **Fattura e consegna** della pagina **Fornitori**.

### <a name="set-up-a-format-for-the-unique-certification"></a>Impostare un formato per la certificazione unica

1. Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.
2. Nella scheda **Ritenuta d'acconto** nel campo **Mapping formato certificazione unica**, definire il formato ER da utilizzare per generare la certificazione unica.

## <a name="generate-the-unique-certification"></a>Generare la certificazione unica

1. Selezionare **Imposta** \>**Dichiarazioni** \> **Ritenuta d'acconto** \> **Certificazione unica**.
2. Selezionare **Nuovo**.

    > [!NOTE]
    > L'anno precedente l'anno della data di sistema corrente viene automaticamente assegnato come anno di riferimento della dichiarazione.

3. Nella sezione **Titolo pagina**, immettere le informazioni sulla società e le informazioni sulla persona responsabile della trasmissione della certificazione unica all'agenzia delle entrate.
4. Selezionare **Genera** per creare le certificazioni per ogni destinatario e compilare automaticamente le altre sezioni. La sezione **Fornitore** contiene l'elenco dei destinatari (fornitori) e i dettagli sui fornitori.
5. Selezionare **Generare dettagli** per immettere i dettagli delle transazioni dei fornitori nella dichiarazione.
6. La sezione **Ritenuta d'acconto** mostra gli importi di ogni certificazione dei fornitori. Gli importi sono calcolati e ordinati per codice ritenuta d'acconto.

## <a name="process-the-unique-certification"></a>Elaborare la certificazione unica

Dopo che la certificazione univoca è stata generata e riempita con i dati, è possibile selezionare **Convalida** per convalidare i dati prima che venga generato il file di output. Dopo la convalida del file di output, selezionare **Esporta** per generare il file di output elettronico nel formato legalmente richiesto.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
