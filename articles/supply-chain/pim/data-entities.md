---
title: Entità dati del prodotto
description: Questo argomento fornisce informazioni sulle diverse entità che possono essere utilizzate per importare ed esportare i dati di prodotto.
author: cvocph
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 1e7bda8cc900a5ae3ebab8e78254c802a627dc6d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243275"
---
# <a name="product-data-entities"></a>Entità dati del prodotto

[!include [banner](../includes/banner.md)]

È necessario utilizzare le entità di dati per importare ed esportare i dati del prodotto. La tabella seguente fornisce dettagli sulle entità di dati relative al prodotto e descrive lo scopo di ognuna.

| Entità | Nome Struttura a oggetti applicativi (AOT) (tipo) | Note |
|--------|-------------------------------------------|-------|
| Prodotti V2 | `EcoResProductV2Entity` | Questa entità viene utilizzata per importare ed esportare prodotti specifici e rappresentazioni generali di prodotti condivisi. Permette di effettuare aggiornamenti. Non supporta operazioni SQL basate su set. È abilitata per Open Data Protocol (OData). |
| Prodotti rilasciati V2 | `EcoResReleasedProductV2Entity` | Questa entità viene utilizzata per importare ed esportare prodotti specifici e rappresentazioni generali di prodotti rilasciati. Permette di effettuare aggiornamenti. Richiede che il prodotto condiviso sia già stato creato. Quando viene importato un nuovo prodotto rilasciato, viene creata una versione del prodotto condiviso. Esistono anche entità separate che possono essere utilizzate per importare ed esportare rappresentazioni generali di prodotto e varianti distinte rilasciate. Questa entità non supporta operazioni SQL basate su set o operazioni di eliminazione. È abilitata per OData. |
| Creazione prodotti rilasciati V2 | `EcoResReleasedProductCreationV2Entity` | Questa entità viene utilizzata per importare prodotti condivisi e prodotti rilasciati in un unico passaggio. Sebbene supporti le esportazioni, l'utilizzo è sconsigliato poiché lo scopo dell'entità è la creazione del prodotto. Non supporta gli aggiornamenti. Supporta un set limitato di campi (campi disponibili nella finestra di dialogo di creazione del prodotto). Non supporta operazioni SQL basate su set. Non è esposta attraverso OData. |
| Varianti prodotto | `EcoResProductVariantEntity` | Questa entità viene utilizzata per importare ed esportare varianti di prodotti condivise. Permette di effettuare aggiornamenti. Richiede che i valori di dimensione siano già stati creati. La chiave di integrazione è il prodotto principale più le dimensioni del prodotto. Questa entità non supporta operazioni SQL basate su set. È abilitata per OData. Supporta operazioni di eliminazione. Non può essere estesa con l'aggiunta di nuove dimensioni del prodotto. |
| Varianti prodotto in base all'identificazione del numero di prodotto | `EcoResProductNumberIdentifiedProductVariantEntity` | Questa entità viene utilizzata per importare ed esportare varianti di prodotti condivise. Permette di effettuare aggiornamenti. Richiede che i valori di dimensione siano già stati creati. La chiave di integrazione è il numero del prodotto (mentre la chiave di integrazione per l'entità **Varianti del prodotto** è la rappresentazione generale del prodotto più le dimensioni del prodotto). |
| Varianti prodotti rilasciati | `EcoResReleasedProductVariantEntity` | Questa entità viene utilizzata per importare ed esportare varianti di prodotti rilasciate. Permette di effettuare aggiornamenti. Richiede che le varianti del prodotto condiviso siano già state create. Quando viene importata una nuova variante del prodotto rilasciato, viene creata una versione della variante del prodotto condiviso. Questa entità non supporta operazioni SQL basate su set. È abilitata per OData. Sebbene supporti le operazioni di eliminazione, tale utilizzo attualmente causa il danneggiamento dei dati a causa di un bug nella piattaforma corrente. Questa entità non può essere estesa con l'aggiunta di nuove dimensioni del prodotto. |
| Varianti prodotto rilasciate in base all'identificazione del numero di prodotto | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | Questa entità è simile all'entità **Varianti del prodotto rilasciato** ma la chiave di integrazione è il numero del prodotto invece della rappresentazione generale del prodotto più le dimensioni del prodotto. Non può essere estesa con l'aggiunta di nuove dimensioni del prodotto. |
| Prodotti rilasciati di vendita | `EcoResSellableReleasedProductEntity` | Questa entità viene utilizzata per esportare solo prodotti vendibili. I prodotti vendibili sono prodotti con le informazioni necessarie per essere utilizzati in un ordine cliente. Le stesse regole valgono quando un prodotto viene convalidato utilizzando la funzione **Convalida** nella pagina **Prodotti rilasciati**. |
| Prodotti specifici rilasciati V2 | `EcoResDistinctProductV2Entity` | Questa entità viene utilizzata per esportare prodotti specifici. Tali prodotti specifici possono essere prodotti, prodotti di sottotipo e varianti di prodotto. |
| Rappresentazioni generali prodotti rilasciati V2 | `EcoResProductMasterV2Entity` | Questa entità viene utilizzata per importare ed esportare rappresentazioni generali di prodotto. Non è abilitata per la gestione dei dati. |
| Articolo - Codice a barre | `EcoResProductBarcodeEntityV3` | Questa entità viene utilizzata per esportare prodotti e codici a barre. Questa entità non consente il rilevamento delle modifiche, gli aggiornamenti o le eliminazioni. Per utilizzare il rilevamento delle modifiche, gli aggiornamenti o le eliminazioni sui codici a barre, utilizzare l'entità **Associazione articolo - codice a barre**. |
| Associazione articolo - codice a barre | `EcoResProductBarcodeAssociationEntity` | Questa entità viene utilizzata per esportare prodotti e codici a barre. Consente il rilevamento delle modifiche, gli aggiornamenti e le eliminazioni. Per utilizzare l'entità, la funzionalità *Miglioramenti articolo - codice a barre* deve essere abilitata nella [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). La chiave di entità è `AssociationID`, che crea l'associazione tra il codice a barre e il prodotto. Per aggiungere il supporto per questa chiave, la tabella `InventitemBarcodeAssociation` verrà popolata per i dati del codice a barre degli articoli esistenti quando si attiva la funzione. La tabella viene popolata utilizzando un processo batch e se la tabella del codice a barre ha un numero elevato di record, potrebbe essere necessario molto tempo per eseguire il processo batch. Pertanto, si consiglia di pianificare l'abilitazione della funzione (e quindi di eseguire il processo batch) in un momento adatto alla programmazione aziendale. |
| Stati del ciclo di vita prodotto | `EcoResProductLifecycleSateEntity` | Questa entità viene utilizzata per importare ed esportare i diversi stati del ciclo di vita del prodotto che possono essere assegnati a un prodotto. |

> [!NOTE]
> È possibile utilizzare l'entità dati **Prodotti rilasciati V2** per importare prodotti nel sistema solo se il prodotto condiviso è già stato creato. Altrimenti, per importare prodotti nel sistema, è necessario utilizzare l'entità dati **Creazione prodotto**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]