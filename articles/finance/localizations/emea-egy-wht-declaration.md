---
title: Dichiarazione della ritenuta d'acconto per l'Egitto
description: In questo argomento viene descritto come configurare e generare le dichiarazioni della ritenuta d'acconto per l'Egitto.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8d78af13e0b3879afd0b6dae7b1a9ece651c3fd2
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2021
ms.locfileid: "7403893"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Dichiarazione della ritenuta d'acconto per l'Egitto (EG-00005)

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Panoramica
In questo argomento viene illustrato come impostare e generare la dichiarazione della ritenuta d'acconto e i moduli 41 e 11 della dichiarazione della ritenuta d'acconto per le persone giuridiche in Egitto 

Tutte le entità egiziane devono preparare il modulo 41 che riassume tutte le imposte trattenute dei fornitori locali e dei fornitori di servizi. Oltre al modulo 41, deve essere generato il modulo 11 per dettagliare tutte le trattenute dei fornitori esteri. 

Il report **Dichiarazione della ritenuta d'acconto** in Dynamics 365 Finance include i seguenti report:

- Modulo dichiarazione n. 41
- Modulo dichiarazione n. 11
    
    
## <a name="prerequisites"></a>Prerequisiti
L'indirizzo principale della persona giuridica deve essere in Egitto.
Nell'area di lavoro **Gestione funzionalità**, la seguente funzionalità deve essere abilitata:

   - **Ritenuta d'acconto globale**

Per ulteriori informazioni su come abilitare le funzionalità, vedere [Panoramica della gestione funzionalità.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. Selezionare **Imposta** > **Impostazione** > **Parametri** > **Parametri di contabilità generale** e quindi nella scheda **Ritenuta d'acconto** impostare l'opzione **Attiva ritenuta d'acconto globale** su **Sì**.
2. Nell'area di lavoro **Creazione di report elettronici**, importare i seguente formati di Creazione di report elettronici dal repository:

    - Excel di dichiarazione RIT (EG)

    > [!NOTE]
    > Il formato sopra è basato sul **Modello di dichiarazione fiscale** e utilizza il **Mapping del modello di dichiarazione fiscale**. Questa configurazione aggiuntiva viene importata automaticamente.

Per ulteriori informazioni su come importare le configurazioni per la creazione di report elettronici, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Scaricare configurazioni per la creazione di report elettronici

L'implementazione dei moduli di dichiarazione RIT per l'Egitto si basa sulle configurazioni per la creazione di report elettronici (ER). Per ulteriori informazioni sulle funzionalità e sui concetti di creazione di report configurabili, vedere [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Per gli ambienti di produzione e test di accettazione dell'utente (UAT), seguire le istruzioni nell'argomento [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Per generare le dichiarazioni della ritenuta d'acconto in una persona giuridica egiziana, è necessario caricare le seguenti configurazioni:

- Tax declaration model.version.82.xml o una versione successiva
- Tax declaration model mapping.version.82.133.xml o versione successiva
- WHT Declaration Excel (EG).version.82.21 o versione successiva

Dopo aver completato il download delle configurazioni ER da Lifecycle Services (LCS) o dal repository globale, completare i seguenti passaggi.

1. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni creazione di report elettronici**.
1. Nella pagina **Configurazioni**, nel riquadro Azioni, selezionare **Exchange > Carica da file XML**.
1. Caricare tutti i file nell'ordine in cui sono elencati nei punti precedenti. Dopo che tutte le configurazioni sono state caricate, l'albero di configurazione deve essere presente in Finance.

## <a name="set-up-application-specific-parameters"></a>Configurare parametri specifici dell'applicazione

I parametri specifici dell'applicazione consentono agli utenti di stabilire i criteri di classificazione e calcolo delle transazioni fiscali in ogni riga di un report generato a seconda della configurazione del **gruppo di articoli di ritenuta d'acconto** o altri criteri stabiliti nella definizione di ricerca.

Il modulo 41 della dichiarazione della ritenuta d'acconto include una colonna specifica in cui la transazione della ritenuta di acconto deve essere classificata in base alla classificazione dell'ufficio tributario denominata **Tipo di codice sconto**. Anziché includere queste nuove classificazioni come nuovi dati di immissione quando le transazioni vengono registrate, le classificazioni saranno determinate in base alle diverse ricerche introdotte in **Configurazioni** > **Configurare parametri specifici dell'applicazione** > **Impostazioni** per soddisfare i requisiti dei report di ritenuta d'acconto per l'Egitto. 

La configurazione seguente viene utilizzata per classificare le transazioni nel report Modulo 41 dichiarazione ritenuta d'acconto:

- **DiscountTaxTypeLookup**-> Colonna n. 18 

Completare i passaggi seguenti per impostare le differenti ricerche utilizzate per generare i report sulla dichiarazione della ritenuta d'acconto e sui libri correlati. 

1. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni** > **Impostazione** per impostare le regole per identificare come le transazioni sono classificate nel report sulla dichiarazione della ritenuta d'acconto. 
2. Selezionare la versione corrente e nella Scheda dettaglio **Ricerche** selezionare il nome della ricerca. Ad esempio, **DiscountTaxTypeLookup**. Questa ricerca identifica l'elenco di tipi di sconto richiesti dall'ufficio tributario.
3. Nella Scheda dettaglio **Condizioni**, selezionare **Aggiungi** e nella nuova riga nella colonna **Risultato della ricerca** selezionare la riga correlata che rappresenta la classificazione nella **Colonna 18**.
4. Nella colonna **Gruppo di articoli ritenuta d'acconto** selezionare il codice correlato utilizzato per identificare la classificazione. Ad esempio, **Sconto consentito**.  
5. Ripetere i passaggi 3 e 4 per tutte le ricerche disponibili.
6. Selezionare di nuovo **Aggiungi** per includere la riga di registrazione finale e nella colonna **Risultato della ricerca**, selezionare **Non applicabile**. 
7. Nelle colonne rimanenti, selezionare **Non vuoto**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Impostazione dei parametri di Contabilità generale

Per generare i report sul modulo della dichiarazione della ritenuta d'acconto in Microsoft Excel, definire un formato ER nella pagina **Parametri di contabilità generale**.

1. Selezionare **Imposta** > **Impostazione** > **Parametri di contabilità generale**.
2. Nella scheda **Ritenuta d'acconto**, nel campo **Mapping formato declarazione ritenuta d'acconto**, selezionare **Excel di dichiarazione RIT (EG)**. Se si lascia il campo vuoto, il report sull'IVA standard verrà generato in formato SSRS.


![Modulo della dichiarazione.](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Genera i moduli della dichiarazione della ritenuta d'acconto
Il processo di preparazione e di invio di un modulo di dichiarazione della ritenuta d'acconto per un periodo specifico si basa sulle transazioni di ritenuta d'acconto registrate durante il processo di liquidazione e registrazione dell'imposta di pagamento. Per ulteriori informazioni sulla ritenuta d'acconto globale, vedere [Ritenuta d'acconto globale](../general-ledger/global-withholding-tax-overview.md).

Completare i seguenti passaggi per generare il report sulla dichiarazione IVA:

1. Selezionare **Imposta** > **Dichiarazioni** > **Ritenuta d'acconto** > **Pagamento ritenuta d'acconto*.
2. Selezionare il periodo di liquidazione, quindi selezionare la data di inizio per il report. 
3. Immettere la data della transazione e quindi selezionare **OK**.
4. Nella finestra di dialogo visualizzata, seleziona uno o più dei tipi di modulo **Modulo n. 41**, **Modulo n. 11** o **Nessuno**. Se si seleziona **Nessuno**, viene generato il report standard. 
5. Selezionare la lingua. Tutti i report vengono tradotti in **en-us** e **ar-eg**.
6. Immettere la filiale e il nome della banca presso la quale verrà effettuato il pagamento dell'imposta.
7. Selezionare il tipo di attività e immettere i numeri di assegno e documento. 
8. Immettere il tipo di entità. 
9. Immettere il nome della persona registrata per assegnare il modulo e selezionare **OK** per confermare la generazione del report. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
