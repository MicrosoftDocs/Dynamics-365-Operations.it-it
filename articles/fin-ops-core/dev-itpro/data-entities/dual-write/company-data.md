---
title: Concetto di società in Dataverse
description: In questo articolo viene descritta l'integrazione dei dati della società tra le app per la finanza e le operazioni e Dataverse.
author: RamaKrishnamoorthy
ms.date: 08/04/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: ad0075e2b92ebeb9fba879bcae503100dc7adb47
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205938"
---
# <a name="company-concept-in-dataverse"></a>Concetto di società in Dataverse

[!include [banner](../../includes/banner.md)]




Nelle app per la finanza e le operazioni, il concetto di *società* è un costrutto sia legale che commerciale. È inoltre un limite di visibilità e di sicurezza per i dati. Gli utenti lavorano sempre nel contesto di una singola società e la maggior parte dei dati è oggetto dello striping della società.

Dataverse non dispone di un concetto equivalente. Il concetto più vicino è *Business Unit*, ovvero principalmente un limite di visibilità e sicurezza per i dati utente. Questo concetto non ha le stesse implicazioni legali o commerciali del concetto di società.

Poiché Business Unit e società non sono equivalenti concetti, non è possibile applicare un mapping di uno-a-uno (1:1) tra loro a scopo dell'integrazione con Dataverse. Tuttavia, poiché gli utenti devono, per impostazione predefinita, poter visualizzare le stesse righe nell'applicazione e in Dataverse, Microsoft ha introdotto una nuova tabella in Dataverse denominata cdm\_Company. Questa tabella equivale alla tabella Società nell'applicazione. Per contribuire a garantire che la visibilità delle righe sia equivalente tra l'applicazione e Dataverse predefinita, è consigliabile la seguente impostazione per i dati in Dataverse:

+ Per ogni riga Company per la finanza e le operazioni abilitata per la doppia scrittura, viene creata una riga cdm\_Company associata.

+ Quando una riga cdm\_Company viene creata e abilitata per la doppia scrittura, una Business Unit predefinita viene creata con lo stesso nome. Sebbene un team di proprietari predefinito venga creato automaticamente per tale Business Unit, la Business Unit non viene utilizzata.
+ Un team proprietario distinto viene creato con lo stesso nome con un suffisso di doppia scrittura. Sarà inoltre associato al Business Unit.

+ Per impostazione predefinita, il proprietario di una riga creata e oggetto di doppia scrittura in Dataverse è impostato sul team "DW Owner" collegato alla Business Unit associata.

Di seguito viene illustrato un esempio di questa impostazione dei dati in Dataverse.

![Impostazione dei dati in Dataverse.](media/dual-write-company-1.png)

Grazie a questa configurazione, qualsiasi riga correlata alla società USMF sarà di proprietà di un team collegato alla Business Unit USMF in Dataverse. Pertanto, qualsiasi utente con diritti di accesso a tale Business Unit tramite un ruolo di sicurezza impostato su visibilità a livello Business Unit potrà visualizzare tali righe. Nel seguente esempio viene illustrato come i team possono essere utilizzati per fornire l'accesso corretto a tali righe.

+ Il ruolo "Sales Manager" viene assegnato ai membri del team "USMF Sales".
+ Gli utenti con il ruolo "Sales Manager" possono accedere a tutte le righe relative ai conti appartenenti alla stessa Business Unit di cui sono membri.
+ Il team "USMF Sales" è collegato alla Business Unit USMF menzionata in precedenza.
+ Di conseguenza, i membri del team "USMF Sales" possono visualizzare qualsiasi conto che appartiene all'utente "USMF DW", proveniente dalla tabella Società USMF nelle app per la finanza e le operazioni.

![Come utilizzare i team.](media/dual-write-company-2.png)

Come mostra la figura precedente, questo mapping 1:1 tra Business Unit, società e team è solo un punto di partenza. In questo esempio, il nuovo Business Unit "Europe" è stata creata manualmente in Dataverse come padre sia per DEMF che ESMF. La nuova Business Unit principale non è correlata alla doppia scrittura. Tuttavia, è possibile utilizzarla per dare ai membri del team "EUR Sales" accesso ai dati dei conti sia in DEMF che in ESMF impostando la visibilità dei dati su **BU padre/figlio** nel ruolo di sicurezza associato.

L'articolo finale da discutere è come la doppia scrittura determina a quale team proprietario assegnare alle righe. Questo funzionamento dipende dalla colonna **Team proprietario predefinito** nella riga cdm\_Company. Quando una riga cdm\_Company è abilitata per la doppia scrittura, un plugin crea automaticamente la Business Unit e il team proprietario (se non esiste già) associati e imposta la colonna **Team proprietario predefinito**. Il amministratore può modificare questa colonna su un valore diverso. Tuttavia, l'amministratore non può cancellare la colonna finché la tabella è abilitata per la doppia scrittura.

> [!div class="mx-imgBorder"]
![Colonna Team proprietario predefinito.](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Striping e bootstrap della società

L'integrazione con Dataverse porta la parità della società utilizzando un identificatore della società per lo striping dei dati. Come nella seguente figura viene illustrato, tutte le tabelle specifiche della società vengono estese in modo che abbiano una relazione molti-a-uno (N:1) con la tabella cdm\_Company.

> [!div class="mx-imgBorder"]
![La relazione N:1 tra una tabella specifica della società e la tabella cdm_Company.](media/dual-write-bootstrapping.png)

+ Per le righe, dopo che una società viene aggiunta e salvata, il valore diventa di sola lettura. Di conseguenza, gli utenti devono assicurarsi di scegliere la società corretta.
+ Solo le righe con dati della società sono idonee alla doppia scrittura tra l'applicazione e Dataverse.
+ Per i dati di Dataverse esistenti, sarà presto disponibile un'esperienza di bootstrap gestita da amministratore.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Compilare automaticamente il nome dell'azienda nelle app di interazione con i clienti

Esistono diversi modi per compilare automaticamente il nome dell'azienda nelle app di interazione con i clienti.

+ Se si è un amministratore di sistema, è possibile impostare la società predefinita accedendo a **Impostazioni avanzate > Sistema > Sicurezza > Utenti**. Aprire il modulo **Utente** e nella sezione **Informazioni sull'organizzazione** impostare il valore **Società predefinita nei moduli**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Impostare l'azienda predefinita nella sezione Informazioni sull'organizzazione.":::

+ Se si dispone dell'accesso in **scrittura** alla tabella **SystemUser** per il livello **Business Unit** è possibile modificare la società predefinita in qualsiasi modulo selezionando una società dal menu a discesa **Società**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Modifica del nome della società in un nuovo account.":::

+ Se si dispone dell'accesso in **scrittura** ai dati in più di una società, è possibile modificare la società predefinita scegliendo una riga che appartiene a una società diversa.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="Scelta di una riga per cambiare la società predefinita.":::

+ Se si è un configuratore o un amministratore di sistema e si desidera compilare automaticamente i dati aziendali in un modulo personalizzato, è possibile utilizzare gli [eventi di modulo](/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Aggiungere un riferimento JavaScript a **msdyn_/DefaultCompany.js** e utilizzare i seguenti eventi. È possibile utilizzare qualsiasi modulo predefinito, ad esempio il modulo **Account**.

    + L'evento **OnLoad** per il modulo: impostare la colonna **defaultCompany**.
    + L'evento **OnChange** per la colonna **Società**: impostare la colonna **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Applicare filtri in base al contesto della società

Per applicare il filtro in base al contesto della società ai moduli personalizzati o alle colonne di ricerca personalizzate aggiunte ai moduli standard, aprire il modulo e utilizzare la sezione **Filtro record correlati** per applicare il filtro della società. È necessario impostarlo per ogni colonna di ricerca che richiede il filtro in base alla società sottostante in una data riga. L'impostazione è mostrata per **Account** nell'illustrazione seguente.

:::image type="content" source="media/apply-company-context.png" alt-text="Applicare il contesto della società.":::



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
