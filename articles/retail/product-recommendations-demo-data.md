---
title: Dati dimostrativi dei consigli sui prodotti omnicanale
description: Questo documento ha lo scopo di fornire una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872328"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Dati dimostrativi dei consigli sui prodotti omnicanale

Questo documento ha lo scopo di fornire una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.

I suggerimenti sul prodotto omnicanale forniscono un set di elenchi di prodotti ordinati curati in modo editoriale o generati a livello di programmazione. Gli elenchi possono essere utilizzati in vari scenari, in base alle esigenze aziendali. Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto.](../commerce/product-recommendations.md)

Per gli ambienti Dynamics di livello 2 e superiore, i suggerimenti sui prodotti vengono calcolati automaticamente in base ai dati dei clienti.
L'uso dei dati dimostrativi dei suggerimenti sui prodotti non disabilita alcuna soluzione di suggerimenti sui prodotti già predisposta nell'ambiente e i costi associati al suo utilizzo.

I suggerimenti sui prodotti degli ambienti di livello 1 si basano solo sui dati dimostrativi statici memorizzati in un file CSV.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Abilitazione dei dati dimostrativi dei suggerimenti sui prodotti in un ambiente

I clienti devono distribuire l'**Estensione dimostrativa dell'anteprima di Dynamics 365 Commerce** al rispettivo ambiente, che abilita automaticamente i dati dimostrativi dei suggerimenti sui prodotti.

## <a name="default-demo-data"></a>Dati dimostrativi predefiniti
Ogni ambiente di tipo Onebox viene fornito con un set precaricato di dati dimostrativi di suggerimenti sui prodotti memorizzati nel file **‘reco_demo_data.csv’**, situato nella stessa cartella di questo documento su Retail Server.

Questi dati sono strutturati nelle seguenti colonne

| Nome colonna         | Obbligatorio          | Descrizione                                                                                                                                 | Valori possibili                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Il tipo di elenco di suggerimenti sul prodotto specifico che deve essere generato dal punto dei dati dimostrativi.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Il numero specifico dell'unità operativa in cui sono previsti i suggerimenti sui prodotti.                                        |                                                                              |
| Categoria            |                    |    La categoria per cui deve essere restituito l'elenco specifico. Se non viene specificata alcuna categoria, l'elenco è solo per la parte superiore della gerarchia di navigazione.    |                                                                              |
| SeedItemId          |                    |    Per gli elenchi che richiedono seed (RecoPeopleAlsoBuy e RecoCart) il prodotto per cui tali elenchi devono mostrare prodotti aggiuntivi.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Uno o più prodotti da restituire come risultato, separati da **‘;’**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Personalizzare i dati dimostrativi
I clienti possono modificare i dati dimostrativi predefiniti con qualsiasi informazione su prodotto e categoria configurata nella sede centrale. Una volta aggiornato il CSV, i suggerimenti sul prodotto restituiti ai clienti rifletteranno immediatamente le modifiche.

L'estensione contiene un file di dati chiamato RecoMockDataset.csv che consente al cliente di controllare il set di dati utilizzato per potenziare i risultati dei suggerimenti simulati. Il nome del file può essere controllato tramite la configurazione dell'estensione usando l'impostazione **ext.Recommendations.DemoFilePath**. I clienti in tal modo posso disporre di più set di dati che possono essere commutati facilmente attraverso la configurazione.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei suggerimenti sul prodotto](../commerce/product-recommendations.md)

[Pianificazione ambiente](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
