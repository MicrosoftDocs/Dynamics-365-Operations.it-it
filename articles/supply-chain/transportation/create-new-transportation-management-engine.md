---
title: Creare un nuovo motore di gestione del trasporto
description: Questo articolo descrive come creare un nuovo motore di gestione del trasporto in Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 627972ef6afb7551bb57821ded24183f8f335e9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857259"
---
# <a name="create-a-new-transportation-management-engine"></a>Creare un nuovo motore di gestione del trasporto

[!include [banner](../includes/banner.md)]

Questo articolo descrive come creare un nuovo motore di gestione del trasporto in Dynamics 365 Supply Chain Management. 

I motori di gestione del trasporto (TMS) definiscono la logica utilizzata per generare ed elaborare le tariffe di trasporto in Gestione trasporto. Supply Chain Management fornisce diversi tipi di motore che calcolano parametri diversi, come tariffe, tempi di transito e il numero di zone che verranno attraversate durante il transito. Questo articolo spiega come utilizzare l'ambiente di sviluppo Microsoft Visual Studio insieme agli strumenti di sviluppo di Supply Chain Management per creare e distribuire un nuovo motore TMS e quindi come configurare il motore in Operations. Per ulteriori informazioni sui motori, vedi [Motori di gestione dei trasporti](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Creare un nuovo motore TMS

Questa sezione spiega come creare una libreria di classi con un'implementazione del motore TMS e come fare riferimento ad essa da un modello di Supply Chain Management.

1. Per distribuire i tuoi nuovi motori, devi disporre di un modello che conterrà i motori. Nel menu **Dynamics 365** &gt; **Gestione dei modelli**, fare clic su **Crea modello** per creare un nuovo modello. Nella prima pagina della guida **Crea modello**, dai un nome al modello **TMSEngines**. 

   [![Creazione di un modello.](./media/012.png)](./media/012.png)

2. Nella pagina successiva, seleziona **Crea nuovo pacchetto**. 

   [![Creazione di un nuovo pacchetto.](./media/021.png)](./media/021.png)

3. Nella pagina successiva, seleziona il modello **ApplicationSuite** a cui fare riferimento. Il modello **ApplicationPlatform** è preselezionato. 

   [![Selezione del modello a cui fare riferimento.](./media/032.png)](./media/032.png)

4. Nella pagina successiva, fai clic su **Fine** per confermare la creazione di un nuovo modello. 

   [![Completamento della creazione del modello.](./media/042.png)](./media/042.png)

5. In una nuova soluzione, crea un nuovo progetto di Supply Chain Management e chiamalo **TMSThirdParty**. Nelle proprietà del progetto, imposta il modello del progetto su **TMSEngines**.
6. Aggiungi una libreria di classe C\# alla tua soluzione e chiamala **ThirdPartyTMSEngines**.
7. Nel progetto ThirdPartyTMSEngines, aggiungi riferimenti agli assembly specifici di Supply Chain Management:
   -   Assembly di applicazioni che consentono di fare riferimento ai tipi X++. Questi gruppi possono essere trovati nelle seguenti posizioni. \[Radice dei pacchetti\] è il percorso della posizione in cui sono posizionati tutti gli assembly distribuiti, ad esempio C:\\Pacchetti.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Assembly di framework che consentono l'accesso a dati, LINQ e funzioni ausiliarie. Tutti questi assembly possono essere trovati nel cestino \[Root dei pacchetti\]\\.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   L'assembly TMS principale (che contiene i motori) e l'assembly di base TMS (che contiene helper, costanti, definizioni di classi di trasferimento dati e così via). Questi gruppi possono essere trovati nelle seguenti posizioni.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Rinomina la classe C\# che viene generato automaticamente nel progetto ThirdPartyTMSEngines per **SampleRatingEngine**.
9. Implementa il motore. Poiché in questo esempio stiamo creando un motore tariffe, ereditiamo dalla classe base per i motori di tasso. La classe base implementa la maggior parte dell'interfaccia del motore tariffe (**TMSFwkIRateEngine**). Non ci resta che implementare il metodo di tasso. Per mantenere questo esempio semplice, faremo in modo che questo il metodo registri una frequenza hardcoded di 100. È possibile creare motori che implementano qualsiasi interfaccia motore, come **TMSFwkIAccessorialEngine**. Tutte le interfacce del motore sono definite in X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Compilare la soluzione.
11. Aggiungi un nuovo riferimento al progetto TMSThirdParty. Il riferimento dovrebbe puntare al progetto ThirdPartyTMSEngines. Quando hai finito, la tua soluzione dovrebbe assomigliare a questa. 

    [![La soluzione, che include un riferimento al progetto TMSThirdParty.](./media/052.png)](./media/052.png)

12. Compilare la soluzione. Verifica che la nuova libreria appaia nel nodo **Riferimenti** in Application Explorer. 

    [![La nuova libreria nel nodo Riferimenti di Application Explorer.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Distribuire il motore TMS come pacchetto

Un modo per distribuire motori TMS di terze parti è tramite un pacchetto di distribuzione. Questo approccio è consigliato in un ambiente di produzione. In un ambiente di sviluppo, è possibile copiare manualmente gli assiemi, come descritto nella sezione successiva "Impostare un motore TMS in Supply Chain Management". Per distribuire il motore come pacchetto, effettuare le seguenti operazioni.

1. Nel menu **Dynamics 365** &gt; **Distribuisci**, fai clic su <strong>Crea pacchetto di distribuzione</strong>.
2. Nella finestra di dialogo **Crea pacchetto di distribuzione**, seleziona il modello TMSEngines e immetti il percorso in cui desideri archiviare i file del pacchetto. 

   [![Selezione del modello TMSEngines.](./media/071.png)](./media/071.png)

3. Ora puoi distribuire il pacchetto nell'ambiente di destinazione. Per un'esercitazione, vedi [Installa un pacchetto distribuibile](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Configurare un motore TMS in Supply Chain Management

Questa sezione spiega come configurare Supply Chain Management per l'utilizzo di un motore TMS e mostra come il nuovo motore che abbiamo creato viene utilizzato nell'acquisto delle tariffe. L'esempio in questa sezione usa i dati dimostrativi della società USMF.

1. Creare un nuovo motore come descritto nella sezione "Crea un nuovo motore TMS".
2. Crea la tua soluzione.
3. Copia l'assembly risultante nella posizione binaria del server Supply Chain Management, cestino \[AOSWebRoot\]. **Nota:** questo passaggio è rilevante solo in un ambiente di sviluppo. In un ambiente di produzione, dovresti distribuire tramite un pacchetto di distribuzione. Per istruzioni, vedi la sezione precedente "Distribuisci il motore TMS come pacchetto".
4. In Supply Chain Management, nella pagina **Motori tariffa**, crea un nuovo motore di valutazione. Il motore deve puntare all'assembly del motore prodotto mediante la creazione della libreria di classi del motore e della classe del motore implementata. 

   [![Creazione di un nuovo motore di tariffa nella pagina Motori di valutazione.](./media/081.png)](./media/081.png)

5. Crea un vettore di spedizione che utilizzi il motore delle tariffe di esempio. Poiché il nostro motore non utilizza alcun dato, non è necessario assegnare un master tariffe. 

   [![Creazione di un nuovo vettore di spedizione.](./media/092.png)](./media/092.png)

6. Nella pagina **Tariffa workbench ciclo di lavorazione**, fai clic su **Valuta negozio**. Dovresti vedere una tariffa di 100 da SampleCarrier, come mostrato nella seguente schermata. In questo esempio, stiamo valutando un carrello tariffe da un ciclo di lavorazione da magazzino 24 al cliente US-004. Tuttavia, poiché la tariffa è codificata, vedrai sempre una tariffa di 100.

   [![Tariffa workbench ciclo di lavorazione.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Suggerimenti e indicazioni

- Se utilizzi strumenti di sviluppo per Supply Chain Management, è utile aggiungere un nuovo progetto alla tua soluzione. Se imposti questo progetto come progetto di avvio e avvii una sessione di debug, puoi eseguire il debug sia di X++ che del codice C\# nella stessa sessione di debug.
- Ogni volta che si modifica e si ricompila il progetto ThirdPartyTMSEngines, è necessario copiare manualmente l'assembly risultante nell'ubicazione binaria o eseguire la distribuzione tramite un pacchetto di distribuzione. In caso contrario, potresti eseguire utilizzando un assembly non aggiornato.
- Dopo aver eseguito operazioni specifiche di TMS in Supply Chain Management, il processo di lavoro di Internet Information Services (IIS) potrebbe bloccare l'assembly ThirdPartyTMSEngines in modo che l'assembly non possa essere aggiornato. In questo caso, riavvia il processo w3svc.

### <a name="whitepaper"></a>White paper

Per ulteriori informazioni, scarica il seguente white paper (scritto per supportare AX2012, ma è ancora valido per Dynamics 365 Supply Chain Management)

- [Implementazione e distribuzione di motori di gestione dei trasporti](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]