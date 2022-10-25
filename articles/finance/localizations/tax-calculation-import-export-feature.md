---
title: Importare ed esportare i calcoli delle imposte
description: Questo articolo fornisce informazioni sulla funzionalità di importazione ed esportazione del servizio di calcolo delle imposte.
author: Kai-Cloud
ms.date: 10/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690235"
---
# <a name="import-and-export-tax-calculations"></a>Importare ed esportare i calcoli delle imposte

Questo articolo fornisce informazioni sulla funzionalità di importazione ed esportazione del servizio di calcolo delle imposte. Questa funzionalità aiuta a garantire un'esperienza di configurazione flessibile ed efficiente.

## <a name="import-and-export-tax-codes"></a>Importare ed esportare i codici imposta

### <a name="export-templates"></a>Esportare i modelli

1. Accedi a [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. Nell'area di lavoro delle **funzioni di globalizzazione** , seleziona **Funzionalità** e quindi il riquadro **Calcolo imposte**.
3. Seleziona una funzione esistente, oppure [crea una nuova funzionalità](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Nella griglia **versioni** seleziona **Modifica**.
5. Nella pagina di funzionalità **Calcolo imposte** imposta la [versione di configurazione](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Nella scheda **Codici imposta**, seleziona **Importa**.
7. Seleziona **Esporta un modello di codice imposta** per scaricare il file **TaxCodesTemplate.zip**.
8. Decomprimi **TaxCodesTemplate.zip**. I modelli di codice imposta sono compressi separatamente in base al valore **Origine calcolo**.
9. Decomprimi **By Net Amount.zip** per ottenere i seguenti file con valori separati da virgole (CSV):

    - **TaxCode.csv** – Immetti i codici imposta.
    - **TaxLimit.csv** – Immetti i limiti d'imposta per ogni codice imposta.
    - **TaxRate.csv** – Immetti le aliquote fiscali per ogni codice imposta.

> [!NOTE]
> Per impostazione predefinita, le voci per il codice imposta **Esempio** sono disponibili nei modelli. Se il codice imposta **Esempio** non viene rimosso dai file CSV, verrà importato nella funzione.

### <a name="import-tax-codes"></a>Importare i codici imposta

Segui questi passaggi per importare il codice imposta **Esempio** nel modello nella funzione di calcolo delle imposte.

1. In RCS, nella pagina della funzionalità **Calcolo imposte**, nella scheda **Codici imposta** seleziona **Importa**.
2. Seleziona **Sfoglia**, trova e seleziona il file **TaxCode.csv** e poi, nel campo **Tabella di destinazione** seleziona **Codice imposta**.
3. Seleziona **OK** per importare il codice imposta.
4. Trova e seleziona il file **TaxRate.csv** e poi, nel campo **Tabella di destinazione** seleziona **Aliquota**.
5. Seleziona **OK** per importare l'aliquota fiscale.
6. Trova e seleziona il file **TaxLimit.csv** e poi, nel campo **Tabella di destinazione** seleziona **Limite imposta**.
7. Seleziona **OK** per importare il limite imposta.

Puoi anche importare direttamente il file zip che include tutti e tre i file CSV. In questo modo puoi completare l'importazione in modo facile e veloce.

1. In RCS, nella pagina della funzionalità **Calcolo imposte**, nella scheda **Codici imposta** seleziona **Importa**.
2. Seleziona **Sfoglia**, trova e seleziona il file **By Net Amount.zip**, quindi seleziona **OK**.

### <a name="export-tax-codes"></a>Esportare i codici imposta

1. In RCS, nella pagina della funzionalità **Calcolo imposte**, nella scheda **Codici imposta** seleziona **Esporta**.

    Il pulsante **Esporta** è disponibile quando è presente almeno un codice imposta nella griglia **Codici imposta**.

2. Seleziona **OK** per esportare tutti i codici imposta della funzionalità in un file zip.

> [!NOTE]
> Utilizza il file esportato come modello per importare i codici imposta nella funzione corrispondente.

## <a name="import-and-export-applicability-rules"></a>Importare ed esportare regole di applicabilità

### <a name="export-applicability-rules"></a>Esportare le regole di applicabilità

1. Accedere a [RCS](https://marketing.configure.global.dynamics.com/).
2. Nell'area di lavoro delle **funzioni di globalizzazione** , seleziona **Funzionalità** e quindi il riquadro **Calcolo imposte**.
3. Seleziona una funzione esistente, oppure [crea una nuova funzionalità](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Nella griglia **versioni** seleziona **Modifica**.
5. Nella pagina di funzionalità **Calcolo imposte** imposta la [versione di configurazione](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Nella scheda **Applicabilità gruppo di imposte** seleziona le righe nella griglia **Imposta applicabilità del gruppo di imposte**.
7. Seleziona il pulsante **Apri in Microsoft Office** quindi seleziona **Matrice di applicabilità dinamica del servizio imposte**.

    [![Esportazione delle regole di applicabilità in Microsoft Excel nella pagina della funzione di calcolo delle imposte.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Seleziona **Scarica** per esportare le righe selezionate in un foglio di lavoro di Microsoft Excel.

### <a name="import-applicability-rules"></a>Importare le regole di applicabilità

Il foglio di lavoro di Excel che hai scaricato contiene la struttura della griglia **Imposta applicabilità del gruppo di imposte**. Puoi aggiungere nuove regole direttamente nel foglio di lavoro. Al termine, segui questi passaggi per importare di nuovo le nuove regole nella griglia **Imposta applicabilità del gruppo di imposte**.

1. Nel foglio di lavoro di Excel, seleziona e copia le righe da importare.
2. In RCS, nella pagina della funzionalità **Calcolo delle imposte**, nella scheda **Applicabilità del gruppo di imposte**, seleziona **Aggiungi** per inserire un record vuoto in fondo alla griglia **Imposta applicabilità del gruppo di imposte**.
3. Seleziona **CTRL+V** per incollare le righe copiate nella griglia.
4. Seleziona **Salva**.

## <a name="import-feature-demo-data"></a>Importare dati demo delle funzionalità

Segui questi passaggi per importare i dati della demo delle funzionalità.

1. Accedere a [RCS](https://marketing.configure.global.dynamics.com/).
2. Nell'area di lavoro delle **funzioni di globalizzazione** , seleziona **Funzionalità** e quindi il riquadro **Calcolo imposte**.
3. Seleziona **Importa**, e poi, nella pagina **Importa funzionalità dal repository globale**, seleziona **Sincronizza**. 
4. Nella tabella, seleziona la funzionalità **tax-calculation-feature-demo-data** funzione, quindi seleziona **Importa**.
5. Seleziona **Visualizza** per rivedere i codici imposta, i gruppi e le regole di applicabilità definiti nella funzionalità importata.
6. In Finance, passa all'entità giuridica **DEMF**, quindi vai a **Imposta** \> **Impostazione** \> **Configurazione imposta** \> **Parametri calcolo imposta**.
7. Nella scheda **Generale**, seleziona **Abilita servizio calcolo imposte**.
8. Nel campo **Nome impostazione funzionalità** , seleziona **tax-calculation-feature-demo-data**.
9. Seleziona un **Periodo di liquidazione** e un **Gruppo di registrazione contabile** per i nuovi codici fiscali demo, quindi seleziona **Conferma**.
10. Seleziona **Salva**.

> [!NOTE]
> La funzionalità demo **tax-calculation-feature-demo-data** si basa sulla versione della funzionalità **40.54.234** e progettata per la persona giuridica demo **DEMF**. Assicurati che Finance e RCS siano aggiornati alla versione 10.0.26 o successiva.
