---
title: Configurare origini dati Ricerca per utilizzare parametri specifici dell'applicazione ER
description: In questo articolo viene descritto come configurare origini dati Ricerca nei formati di Creazione di report elettronici (ER) per utilizzare parametri specifici dell'applicazione ER.
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 193f185e0b7a7183f98bf9aff3fd3e1c4589fb58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892539"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Configurare origini dati Ricerca per utilizzare parametri specifici dell'applicazione ER 

[!include[banner](../includes/banner.md)]

La funzionalità Parametri specifici dell'applicazione [Creazione di report elettronici (ER)](general-electronic-reporting.md) ti consente di configurare il filtro dati in un formato ER in modo che sia basato su un set di regole astratte. Questo set di regole può essere configurato per utilizzare l'origine dati di tipo **Ricerca** disponibile in un formato ER. Puoi quindi specificare regole reali oltre i designer di componenti ER utilizzando l'interfaccia utente (IU) che viene generata automaticamente in base alle impostazioni dell'origine dati **Ricerca** del formato ER corrispondente e ai dati della persona giuridica corrente. Alla fine, le regole specificate saranno accessibili tramite l'origine dati **Ricerca** del formato ER quando viene eseguito questo formato ER.

> [!NOTE]
> Utilizza le origini dati configurate del formato ER modificabile per specificare quali dati dell'applicazione vengono utilizzati per configurare regole reali.

Usa la [pagina di progettazione Operazioni ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) per portare un'origine dati di tipo **Ricerca** nel formato ER. L'origine dati deve essere configurata per descrivere l'aspetto delle regole astratte, incluso quanto segue:

   - Il set di parametri di un determinato tipo di dati il cui valore viene fornito per specificare una singola regola.
   - Il tipo di valore di un determinato tipo di dati restituito da una singola regola quando questa regola è considerata la più appropriata.

Puoi configurare i seguenti tipi di origini dati **Ricerca** a seconda del tipo di valore restituito da qualsiasi regola configurata:

   - Usa il tipo **Modello dati\Ricerca** quando deve essere restituito un valore di enumerazione modello.
   - Usa il tipo **Dynamics 365 Operations\Ricerca** quando un valore di enumerazione dell'applicazione o un valore [tipo di dati esteso](../extensibility/extensible-edts.md) dell'applicazione deve essere restituito.
   - Usa il tipo **Enumerazione formato\Ricerca** quando deve essere restituito un valore di enumerazione formato.

L'illustrazione seguente mostra come configurare un'enumerazione formato nel formato ER di esempio.

   ![Visualizzazione di un'enumerazione formato come base per l'origine dati di ricerca configurata.](./media/er-lookup-data-sources-img1.gif)

La seguente illustrazione mostra i componenti di formato che sono stati configurati per segnalare diversi tipi di imposte in una sezione diversa di un report generato.

   ![Visualizzazione delle sezioni formato per segnalare separatamente tipi diversi di imposte.](./media/er-lookup-data-sources-img2.png)

L'illustrazione seguente mostra come la pagina di progettazione Operazioni ER consente l'aggiunta di un'origine dati di tipo **Enumerazione formato\Ricerca**.  L'origine dati aggiunta è configurata per restituire un valore dell'enumerazione formato `List of taxation levels`.

   ![Aggiunta di un'origine dati ER del tipo Enumerazione formato\Ricerca.](./media/er-lookup-data-sources-img3.gif)

L'illustrazione seguente mostra come l'origine dati aggiunta è configurata per utilizzare il campo **Codice** dell'elenco di record **Model.Data.Tax** dell'origine dati **Modello** come parametro che deve essere specificato per ogni regola configurata.

![Configurazione dei parametri dell'origine dati aggiunta del tipo Enumerazione formato\Ricerca.](./media/er-lookup-data-sources-img4.gif)

L'origine dati `Model.Data.Tax` aggiunta è configurata per specificare un codice fiscale per ogni regola configurata accedendo ai record della tabella dell'applicazione **TaxTable**.

   ![Esame dell'origine dati di ricerca di una singola società di tipo Enumerazione formato\Ricerca.](./media/er-lookup-data-sources-img5.gif)

È possibile impostare le regole di ricerca per il formato ER selezionato utilizzando l'interfaccia utente allineata automaticamente con la struttura dell'origine dati configurata. Attualmente, questa interfaccia utente richiede per ogni regola la definizione del valore restituito come valore di enumerazione formato `List of taxation levels` e del codice fiscale come parametro.

   ![Impostare le regole per l'origine dati configurata.](./media/er-lookup-data-sources-img6.gif)

L'illustrazione seguente mostra come l'origine dati `Model.Data.Summary.LevelByLookup` di tipo **Campo calcolato** può essere configurata per chiamare l'origine dati **Ricerca** configurata fornendo i parametri richiesti. Per elaborare questa chiamata al runtime, ER esamina l'elenco di regole configurate nella sequenza definita per individuare la prima regola che soddisfa le condizioni fornite. In questo esempio, è la regola che contiene il codice fiscale che corrisponde a quello fornito. Di conseguenza, viene trovata la regola più appropriata e il valore di enumerazione configurato per la regola trovata viene restituito da questa origine dati.

> [!NOTE]
> Viene generata un'eccezione quando non viene trovata alcuna regola applicabile. Per evitare queste eccezioni, configurare ulteriori regole alla fine dell'elenco di regole per gestire i casi in cui viene fornito un valore non configurato o nessun valore. Usate di conseguenza le opzioni **\*Not blank**\* e **\*Blank**\* .  
>
> ![Aggiungere un'origine dati per chiamare l'origine dati Ricerca configurata.](./media/er-lookup-data-sources-img7.png)

Quando imposti l'opzione **Interaziendale** su **Sì** per l'origine dati di ricerca modificabile, aggiungi un nuovo parametro **Società** al set di parametri di questa origine dati. Il valore del parametro **Società** deve essere specificato al runtime quando viene chiamata l'origine dati di ricerca. Quando il codice della società viene specificato al runtime, le regole configurate per questa società vengono utilizzate per trovare la regola più appropriata e viene restituito il valore corrispondente. La seguente illustrazione mostra come eseguire questa operazione e come viene modificato il set di parametri dell'origine dati modificabile.

   ![Esaminare l'origine dati di ricerca interaziendale di tipo Enumerazione formato\Ricerca.](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Seleziona ogni società separatamente per configurare il set di regole per questa origine dati di ricerca del formato ER modificabile. Viene generata un'eccezione al runtime quando la ricerca interaziendale viene chiamata con il codice dell'azienda per la quale l'impostazione di ricerca non è stata completata.
>
> Assicurati di concedere le autorizzazioni per un utente che esegue il formato ER con l'origine dati **Ricerca** per accedere ai dati di ogni società che rientra nell'ambito di questa origine dati. Altrimenti, viene generata un'eccezione al runtime.

Le funzionalità estese dell'origine dati **Ricerca** sono disponibili a partire dalla versione 10.0.19. Quando imposti l'opzione **Esteso** su **Sì** per l'origine dati di ricerca modificabile, l'origine dati di ricerca configurata viene trasformata nell'origine dati strutturata che offre le funzionalità aggiuntive per analizzare il set di regole configurato. Nella figura seguente viene illustrata questa trasformazione.

   ![Esaminare l'origine dati di ricerca strutturata di tipo Enumerazione formato\Ricerca.](./media/er-lookup-data-sources-img9.gif)

- L'elemento secondario **Ricerca** è progettato come funzione per trovare la regola più appropriata nel set di regole configurabili in base al set di parametri fornito.
- L'elemento secondario **IsLookupResultSet** è progettato come funzione per accettare il valore fornito dell'origine dati di enumerazione di base e restituire il valore *Booleano* **True** quando il set di regole contiene almeno una regola per la quale il valore di enumerazione fornito è stato configurato come valore restituito. Questa funzione restituisce il valore *Booleano* **False** quando non ci sono regole configurate per restituire il valore di enumerazione fornito.
- L'elemento secondario **Impostazione** è progettato come funzione che restituisce il set di regole configurate come record di un elenco di record. I valori restituiti e il set di parametri delle regole configurate sono presentati in ogni record restituito come campi di tipi di dati pertinenti:

    - Il valore restituito viene presentato come campo **Risultato della ricerca**.
    - I parametri configurati sono presentati come campi con nomi di parametri (il campo **Codice** in questo esempio).

Per ulteriori informazioni su come configurare l'origine dati **Ricerca**, vedi [Configurare i formati ER per utilizzare parametri specificati per persona giuridica](er-app-specific-parameters-configure-format.md). Per informazioni su come impostare le regole di ricerca, vedi [Impostare i parametri di un formato ER per persona giuridica](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare i formati ER per utilizzare i parametri specifici per la persona giuridica](er-app-specific-parameters-configure-format.md)

[Impostare i parametri di un formato ER per la persona giuridica](er-app-specific-parameters-set-up.md)
