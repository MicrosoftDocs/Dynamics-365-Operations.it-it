---
title: Importare ed esportare i calcoli delle imposte
description: Questo articolo fornisce informazioni sulla funzionalità di importazione ed esportazione del servizio di calcolo delle imposte.
author: Kai-Cloud
ms.date: 11/22/2021
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
ms.openlocfilehash: 9daee683763d7cb0eb9573497eb4e20cba9b1863
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855175"
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
