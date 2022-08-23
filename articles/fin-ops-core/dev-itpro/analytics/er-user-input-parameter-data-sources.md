---
title: Utilizzare le origini dati USER INPUT PARAMETER per specificare i parametri per un report
description: Questo articolo spiega come utilizzare le origini dati USER INPUT PARAMETER per specificare i parametri per i report da generare.
author: kfend
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: c6d0f1a0d9c5eb70a9812459a25d5b14407cce7a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278709"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Utilizzare le origini dati USER INPUT PARAMETER per specificare i parametri per un report

[!include[banner](../includes/banner.md)]

Quando progetti i componenti [mapping del modello](er-overview-components.md#model-mapping-component) e [formato ER](er-overview-components.md#format-component) della [creazione di report elettronici](general-electronic-reporting.md) (ER) puoi utilizzare le origini dati di tipo *PARAMETRO INPUT UTENTE* per ottenere i valori richiesti che possono essere specificati nei campi di immissione dati nella finestra di dialogo in fase di esecuzione, prima che inizi l'esecuzione di un formato ER. Questo articolo descrive le origini dati *PARAMETRO INPUT UTENTE* attualmente supportate.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Proprietà obbligatorie

È necessario specificare le seguenti proprietà per le origini dati di tipo *PARAMETRO INPUT UTENTE*:

- Nel campo **Nome** immetti il nome interno dell'origine dati. Puoi usare questo nome in altre [espressioni](er-formula-language.md) e associazioni del mapping di modello configurato o del componente di formato.

## <a name="optional-properties"></a><a name="optional-properties"></a>Proprietà facoltative

Puoi facoltativamente specificare le seguenti proprietà per le origini dati di tipo *PARAMETRO INPUT UTENTE*:

- Nel campo **Etichetta** specifica l'etichetta utilizzata per il relativo campo di immissione dati nella finestra di dialogo in fase di esecuzione. È possibile aggiungere un testo di etichetta diverso per codici di lingua diversi attivando il campo **Etichetta** e quindi selezionando **Traduci**.
- Nel campo **Guida** specifica il testo della guida che viene visualizzato in fase di progettazione nella parte inferiore della pagina **Progettazione formato** o della pagina **Progettazione mapping di modello** quando un'origine dati modificabile di tipo *PARAMETRO INPUT UTENTE* è selezionata. Questo testo potrebbe fornire ulteriori dettagli sull'origine dati per aiutare gli utenti durante la configurazione del formato modificabile o del componente di mapping di modello. È possibile aggiungere testi di guida diversi per codici di lingua diversi selezionando **Traduci**.

    > [!NOTE]
    > Il pulsante **Traduci** che puoi utilizzare per aggiungere [etichette e testi specifici della lingua](er-design-multilingual-reports.md#format-component) diventa disponibile solo dopo aver aggiunto l'origine dati, aver salvato le modifiche e quindi aver riaperto l'origine dati per la modifica.

- Nel campo **Sola lettura** configura un'espressione che restituisce un valore *[booleano](er-formula-supported-data-types-primitive.md#boolean)*.

    - Se l'espressione configurata restituisce un valore **Vero** in fase di esecuzione, il relativo campo di immissione dei dati viene visualizzato in grigio nella finestra di dialogo e non è possibile modificarne il valore.
    - Se l'espressione configurata restituisce un valore **Falso** in fase di esecuzione, o se non è configurata alcuna espressione, il relativo campo di immissione dei dati è disponibile nella finestra di dialogo e puoi modificarne il valore.

- Nel campo **Valore predefinito** configura un'espressione che restituisca il valore del tipo di parametro di riferimento. Questo valore può essere utilizzato per compilare un valore predefinito per il relativo campo di immissione dati nella finestra di dialogo in fase di esecuzione.

    Quando si esegue un formato ER, il valore immesso nel relativo campo di immissione dati nella finestra di dialogo in fase di esecuzione viene salvato in memoria come valore utilizzato in precedenza. I valori utilizzati in precedenza vengono salvati individualmente per ciascun campo, formato ER in esecuzione, utente corrente e organizzazione (azienda) corrente.

    - Imposta l'opzione **Ripristina sempre il valore predefinito** su **sì** se il valore restituito dall'espressione **Valore predefinito** deve essere sempre utilizzato come valore predefinito, indipendentemente dal valore utilizzato in precedenza.
    - Imposta l'opzione **Ripristina sempre il valore predefinito** su **no** se il valore restituito dall'espressione **Valore predefinito** deve essere utilizzato come valore predefinito solo quando il valore utilizzato in precedenza è mancante.

    > [!NOTE]
    > Se imposti l'opzione **Ripristina sempre il valore predefinito** su **sì**, è necessario configurare un'espressione nel campo **Valore predefinito**.

- Se imposti l'opzione **Consenti selezione multipla** su **sì**, è possibile selezionare più valori per il parametro configurato in fase di esecuzione. Se la imposti su **No**, puoi selezionare un solo valore.

    > [!NOTE]
    > Questa opzione non è applicabile a tutti i tipi *PARAMETRO INPUT UTENTE*. In fase di progettazione, viene generata un'eccezione per informare l'utente che il parametro di input utente configurato non supporta la selezione multipla e che è possibile selezionare o immettere un solo valore.
    >
    > Se imposti l'opzione **Consenti selezione multipla** su **sì**, e hai specificato un'espressione nel campo **Valore predefinito**, quell'espressione può essere utilizzata per impostare un solo valore predefinito.

- Seleziona l'opzione **Modifica visibilità** per specificare se il parametro configurato deve essere visualizzato nella finestra di dialogo in fase di esecuzione.

    > [!NOTE]
    > La visibilità predefinita delle origini dati di tipo *PARAMETRO INPUT UTENTE* dipende dal componente ER che li contiene.
    >
    > - Se un'origine dati è configurata nel componente formato, è visibile per impostazione predefinita.
    > - Se un'origine dati è configurata nel componente di mapping di modello, è visibile solo se il valore dell'origine dati influisce sul risultato quando viene eseguito un componente ER. Ad esempio, hai aggiunto un'origine dati ma non l'hai utilizzata nelle espressioni e nelle associazioni del componente di mapping di modello corrente. In questo caso, per impostazione predefinita, il relativo campo di immissione dati non verrà visualizzato nella finestra di dialogo in fase di esecuzione. 

    Sulla pagina **Progettazione formule** nel campo **Formula** configura un'espressione che restituisca un valore *booleano*.

    - Se l'espressione configurata restituisce un valore **Vero** in fase di esecuzione, o se non è configurata alcuna espressione, il relativo campo di immissione dei dati è visibile nella finestra di dialogo in fase di esecuzione.
    - Se l'espressione configurata restituisce un valore **Falso**, il relativo campo di immissione dei dati è nascosto nella finestra di dialogo in fase di esecuzione. Quando viene chiamato da altre espressioni in fase di esecuzione, restituisce il valore predefinito, il valore utilizzato in precedenza o il valore predefinito per il valore del tipo di dati corrente, a seconda di altre impostazioni.

## <a name="type-specific-properties"></a>Proprietà specifiche del tipo

### <a name="application-dependent-user-input-parameter"></a>Parametro input utente dipendente dall'applicazione

Utilizza un'origine dati di tipo **Generale** \> **Parametro input utente** per ottenere il valore o i valori richiesti di un tipo di dati specificato per l'istanza corrente dell'applicazione Microsoft Dynamics 365 Finance. Quando aggiungi un'origine dati di questo tipo a un componente ER, specifica le seguenti proprietà:

- Nel campo **Nome del tipo di dati delle operazioni (EDT, enum)**, seleziona un [tipo di dati esteso (EDT)](../extensibility/extensible-edts.md) o un'enumerazione dell'applicazione.

> [!NOTE]
> Ti consigliamo di rivedere le espressioni configurate nei campi **Sola lettura** e **Valore predefinito** quando modifichi il riferimento **Nome del tipo di dati delle operazioni (EDT, enum)** in un'origine dati modificabile di questo tipo *PARAMETRO INPUT UTENTE*.

L'illustrazione seguente mostra le proprietà dell'origine dati `$TaxRegNum` configurata nella configurazione del formato ER **Instat XML (DE)**. Questa origine dati è configurata per utilizzare il tipo di dati esteso *Descrizione* per offrire il campo di immissione dati **Numero di registrazione fiscale** nella finestra di dialogo in fase di esecuzione.

![Le proprietà di un'origine dati di tipo PARAMETRO INPUT UTENTE nella finestra di dialogo della pagina Progettazione formato.](./media/er-user-input-parameter-data-sources-01.png)

L'illustrazione seguente mostra la finestra di dialogo che viene mostrata in fase di esecuzione quando la configurazione del formato ER **Instat XML (DE)** viene eseguita per [creare](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) la dichiarazione Intrastat. Nota che il campo **Numero di registrazione fiscale** configurato è disponibile per l'inserimento dei dati.

![Finestra di dialogo Report Intrastat del formato ER in esecuzione nella pagina Intrastat.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Parametro di input utente  per enumerazione modello dati

Utilizza un'origine dati di tipo **Modello di dati** \> **Parametro di input dell'utente di enumerazione** per ottenere il valore o i valori richiesti di una singola [enumerazione](er-formula-supported-data-types-primitive.md#enumeration) del modello di dati. Quando aggiungi un'origine dati di questo tipo a un componente ER, specifica le seguenti proprietà:

- Nel campo **Modello** specifica un riferimento al modello di dati di base.
- Nel campo **Enumerazione del modello** specifica un riferimento a un'enumerazione del modello di dati di riferimento.
- Nel campo **Versione** seleziona il numero di revisione del componente del modello di dati ER che contiene l'enumerazione del modello di riferimento.

    > [!TIP]
    > In fase di progettazione, puoi lasciare il campo **Versione** vuoto per accedere all'elenco delle enumerazioni per il componente del modello di dati di riferimento che risiede nella versione bozza della configurazione del modello di dati ER corrispondente. In questo modo è possibile modificare contemporaneamente la versione bozza del componente di mapping o formato di modello e la versione bozza del componente del modello di dati di base.
    >
    > Tuttavia, nota che il campo **Versione** può essere lasciato vuoto solo nella versione di bozza di un mapping di modello o di un componente di formato. Quando si modifica lo stato di una configurazione di un mapping di modello ER o formato da **Bozza** a **Completato**, questo campo viene compilato automaticamente dal numero di revisione del modello più alto disponibile nell'istanza di Finance corrente. Se introduci una nuova enumerazione o un nuovo valore di enumerazione nella versione bozza del modello di dati di base e vi fai riferimento nel mapping di modello modificabile o nel componente di formato, completa la versione bozza della configurazione del modello di dati di base prima che la versione bozza della configurazione del mapping di modello ER o del formato venga completata. In caso contrario, verrà generata un'eccezione "Percorso non trovato" quando si modifica lo stato della configurazione del mapping di modello o del formato da **Bozza** a **Completato**. Il messaggio informerà che l'enumerazione di riferimento o il valore di enumerazione manca nel modello di dati di base.

L'illustrazione seguente mostra le proprietà dell'origine dati `$ReportDirection` configurata nella configurazione del formato ER **Instat XML (DE) Contoso**. La configurazione **Instat XML (DE) Contoso** è [derivata](general-electronic-reporting.md#Configuration) dalla configurazione **Instat XML (DE)**. Questa origine dati è configurata per utilizzare l'enumerazione di modello *ReportDirection* per offrire il campo di ricerca appropriato nella finestra di dialogo in fase di esecuzione.

![Le proprietà dell'origine dati di tipo PARAMETRO INPUT UTENTE nella finestra di dialogo della pagina Progettazione formato.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Parametro di input utente enumerazione formato

Utilizza un'origine dati di tipo **Enumerazione formato** \> **Parametro di input dell'utente di enumerazione** per ottenere il valore o i valori richiesti di una singola enumerazione del formato. Quando aggiungi un'origine dati di questo tipo a un componente ER, specifica le seguenti proprietà:

- Nel campo **Enumerazione formato** specifica un'enumerazione del formato modificabile.

> [!NOTE]
> Le origini dati di questo tipo possono essere configurate solo nell'ambito del componente di formato modificabile.

## <a name="additional-resources"></a>Risorse aggiuntive

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Avviare i valori dell'origine dati del tipo USER INPUT PARAMETER dal codice sorgente](er-initiate-uip-data-source-value-from-source-code.md)
