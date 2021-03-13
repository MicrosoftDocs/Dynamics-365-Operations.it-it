---
title: Abilitare le previsioni di pagamento del cliente (anteprima)
description: Questo argomento spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Informazioni finanziarie dettagliate.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009420"
---
# <a name="enable-customer-payment-predictions-preview"></a>Abilitare le previsioni di pagamento del cliente (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Informazioni finanziarie dettagliate. Puoi attivare la funzionalità nell'area di lavoro **Gestione funzionalità** e immettere le impostazioni di configurazione nella pagina **Parametri di Informazioni finanziarie dettagliate**. Questo argomento include anche informazioni che possono aiutarti a utilizzare efficacemente la funzionalità.

> [!NOTE]
> Prima di completare i passaggi seguenti, assicurati di completare i passaggi prerequisiti nell'argomento [Configurare Informazioni finanziarie dettagliate](configure-for-fin-insites.md).

1. Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente. Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox. Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > Se la tua distribuzione di Microsoft Dynamics 365 Finance è una distribuzione di Service Fabric, puoi saltare questo passaggio. Il team di Informazioni finanziarie dettagliate dovrebbe aver già attivato la versione di anteprima per te. Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta  <fiap@microsoft.com>.

2. Attiva la funzionalità Informazioni sui pagamenti del cliente:

    1. Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
    2. Trova la funzionalità denominata **Informazioni sui pagamenti dei clienti (anteprima)**.
    3. Selezionare **Abilita ora**.

    La funzione Informazioni sui pagamenti del cliente è ora attivata e pronta per essere configurata.

3. Configura la funzionalità Informazioni sui pagamenti del cliente:

    1. Vai a **Credito e riscossioni \> Imposta \> Informazioni finanziarie dettagliate \> Parametri di Informazioni finanziarie dettagliate**.

        [![Pagina dei parametri delle informazioni finanziarie dettagliate prima della configurazione della funzione](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. Nella pagina **Parametri di Informazioni finanziarie dettagliate**, nella scheda **Informazioni dettagliate sui pagamenti dei clienti**, seleziona il collegamento **Visualizza i campi dati utilizzati nel modello di previsione** per aprire la pagina **Campi dati per il modello di previsione**. Qui puoi visualizzare l'elenco predefinito dei campi utilizzati per creare il modello di previsione dell'intelligenza artificiale (AI) per le previsioni di pagamento dei clienti.

        Per utilizzare l'elenco di campi predefinito per creare il modello di previsione, chiudi la pagina **Campi dati per il modello di previsione**, quindi nella pagina **Parametri di Informazioni finanziarie dettagliate**, imposta l'opzione **Abilita funzionalità** su **Sì**.

    3. Specifica il periodo di transazione "molto in ritardo" per definire cosa significa il bucket di previsione **Molto tardi** per la tua azienda.

        Per ogni fattura aperta, il sistema prevede la probabilità di pagamento in tre bucket: **Puntuale**, **In ritardo** e **Molto in ritardo**.

        - **Puntuale**: questo bucket include i pagamenti che si prevede verranno pagati entro la data di scadenza della transazione.
        - **In ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo la data di scadenza della transazione ma prima dell'inizio del periodo di transazione "molto in ritardo".
        - **Molto in ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo l'inizio del periodo di transazione "molto in ritardo".

        > [!NOTE]
        > Se modifichi il periodo di transazione "molto in ritardo" e selezioni **Modifica la soglia di ritardo** dopo che il modello di previsione IA per i pagamenti dei clienti è stato creato, il modello di previsione esistente viene eliminato e viene creato un nuovo modello. Il nuovo modello di previsione sposterà le transazioni nel periodo "molto in ritardo" in base alle impostazioni immesse per definirlo.

    4. Dopo aver finito di definire il periodo di transazione "molto in ritardo", seleziona **Crea modello di previsione** per creare il modello di previsione. La sezione **Modello di previsione** nella pagina **Parametri di Informazioni finanziarie dettagliate** mostra lo stato del modello di previsione.

        > [!NOTE]
        > In qualsiasi momento durante la creazione del modello di previsione, puoi selezionare **Reimposta la creazione del modello** per riavviare il processo.

    La funzionalità è ora configurata è pronta per essere utilizzata.

Dopo che la funzionalità è stata attivata e configurata e il modello di previsione è stato creato e funziona, la sezione **Modello di previsione** della pagina **Parametri di informazioni finanziarie dettagliate** mostra la precisione del modello, come visualizzato nell'illustrazione seguente.

[![Precisione del modello di previsione nella pagina Parametri di informazioni finanziarie dettagliate](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Dettagli del rilascio

È disponibile un'anteprima pubblica di Informazioni dettagliate finanziarie per le distribuzioni di valutazione negli Stati Uniti, in Europa e nel Regno Unito. Microsoft sta aggiungendo in modo incrementale il supporto per più aree geografiche.

Le funzionalità di anteprima pubblica possono e devono essere attivate solo negli ambienti sandbox di livello 2. I modelli di configurazione e intelligenza artificiale creati in un ambiente sandbox non possono essere migrati in un ambiente di produzione. Per ulteriori informazioni, vedi [Condizioni integrative per le versioni di anteprima di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Informativa sulla privacy

Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.
