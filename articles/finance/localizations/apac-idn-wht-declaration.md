---
title: Report di ritenuta d'acconto per l'Indonesia
description: In questo articolo viene descritto come configurare e generare i report di ritenuta d'acconto per l'Indonesia.
author: AdamTrukawka
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.search.scope: ''
ms.openlocfilehash: 732db563532ebc46c7b9fc69c2aaa128640084f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282437"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Report di ritenuta d'acconto per l'Indonesia (ID-00005)

[!include [banner](../includes/banner.md)]

Questo articolo spiega come impostare e generare il file della ritenuta d'acconto PPH che le persone giuridiche in Indonesia utilizzano per segnalare le transazioni di ritenuta nell'applicazione e-Bupot.

L'autorità fiscale indonesiana (DGT) stabilisce che gli imprenditori tassabili (PKP) che sono registrati presso KPP Pratama come detentori di ritentuta d'acconto/esattore di imposta sul reddito (PPh) Articolo 23 e/o articolo 26 devono dichiarare elettronicamente gli articoli 23 e 26 della dichiarazione dei redditi utilizzando l'applicazione e-Bupot. 

- **Articolo 23** – Il report include tutte le transazioni di ritenuta d'acconto da fornitori in cui il codice paese/regione dell'indirizzo principale è il codice per l'Indonesia.
- **Articolo 26** – Il report include tutte le transazioni di ritenuta d'acconto da fornitori in cui il codice paese/regione dell'indirizzo principale non è il codice per l'Indonesia.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Indonesia.
- La funzionalità **Ritenuta d'acconto globale** deve essere abilitata nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni su come abilitare le funzionalità, vedere [Panoramica della gestione funzionalità.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>Scaricare configurazioni per la creazione di report elettronici

La generazione di un file di importazione si basa sulle configurazioni dei report elettronici (ER). Per ulteriori informazioni sulle funzionalità e sui concetti di creazione di report configurabili, vedere [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Per gli ambienti di produzione e test di accettazione dell'utente (UAT), segui le istruzioni in [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Per generare il file di importazione, carica le seguenti configurazioni dal repository:

- **Tax declaration model.version.93.xml** o una versione successiva
- **Tax declaration model mapping.version.93.153.xml** o una versione successiva
- **WHT PPh schema import (ID).version.93.14**  o una versione successiva

## <a name="set-up-general-ledger-parameters"></a>Impostazione dei parametri di Contabilità generale

1. Vai a **Imposta** \> **Impostazione** \> **Parametri di contabilità generale**.
2. Nella scheda **Ritenuta d'acconto**, nel campo **Mapping formato declarazione ritenuta d'acconto**, seleziona **WHT PPh schema import (ID)**. 
3. Vai a **Imposta** \> **Impostazione** \> **Ritenuta d'acconto** \> **Tipi di ricavi ritenuta d'acconto** per impostare il tipo di ricavi ritenuta d'acconto **Kode Bukti Potong** e quindi assegnare i codici ai gruppi di ritenuta d'acconto articolo correlati. I codici sono necessari per generare il file di integrazione utilizzando l'applicazione e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Generare il file di importazione della ritenuta d'acconto

Il processo di preparazione e di generazione del file e-Bupot per un periodo specifico si basa sulle transazioni di ritenuta d'acconto registrate durante il processo di liquidazione o registrazione dell'imposta di pagamento.

Per generare il file, segui questi passaggi.

1. Vai a **Imposta** \> **Dichiarazioni** \> **Ritenuta d'acconto** \> **PPH import file e-bupot 23 and 26**.
2. Seleziona la data di inizio e di fine per il report e quindi il periodo di liquidazione.
3. Immetti la data della transazione e quindi seleziona **OK**.
4. Selezionare la lingua. Tutti i report sono tradotti in inglese americano (**en-us**) e indonesiano (**id**).
5. Seleziona il tipo di attività e immetti i numeri di assegno e documento. 
6. Controlla se il report è stato firmato dal manager. Queste informazioni verranno incluse nel file. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
