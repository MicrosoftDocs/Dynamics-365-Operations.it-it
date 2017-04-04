---
title: Impostare il mandato di addebito diretto SEPA.
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Impostare il mandato di addebito diretto SEPA.



Un addebito diretto SEPA (Single Euro Payment Area) consente al creditore di prelevare denaro dal conto corrente bancario del cliente, purché il cliente abbia concesso un mandato firmato al creditore. Il mandato firmato dal cliente autorizza il creditore a riscuotere un pagamento e istruisce la banca del cliente a effettuare il pagamento. In questo argomento è organizzato per visualizzare il processo per l'installazione dei mandati di addebito diretto SEPA.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

| Categoria       | Prerequisito                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paese | L'indirizzo principale della persona giuridica deve essere nei seguenti paesi: Austria, Belgio, Germania, Spagna, Francia, Italia o i Paesi Bassi. |

1. Impostare una sequenza numerica per i mandati che di addebito ogni ordine di pagamento in addebito diretto deve essere un numero univoco. Utilizzare la pagina **Sequenze numeriche** per creare una sequenza numerica per i mandati di addebito diretto. Questo identificatore servirà ad assegnare la sequenza numerica al sistema di mandato di addebito diretto nella pagina **Parametri contabilità clienti**.

2. Impostare i parametri di contabilità clienti per i mandati di addebito diretto utilizzano ** parametri di contabilità clienti ** impaginano per impostare i parametri per i mandati di addebito diretto. Per impostare i parametri, ** addebito diretto ** nella scheda, modificare i parametri predefiniti come ordinati. Quindi, ** sequenze numeriche ** nella scheda, aggiornare ** ID di fallback di addebito diretto ** campo relativo alla sequenza numerica impostata in precedenza.

3. Impostare un metodo di pagamento per i mandati che di addebito è necessario impostare un metodo di pagamento per i mandati di addebito diretto. Si utilizza questo metodo di pagamento per eseguire query sulle fatture per le quali generare i pagamenti in addebito diretto. Utilizzare la pagina **Metodi di pagamento**per impostare il metodo di pagamento. Per impostare un metodo di pagamento per i mandati di addebito diretto, è necessario completare questi passaggi aggiuntivi per un metodo di pagamento:

-   Nel campo **Tipo di pagamento** selezionare **Pagamento elettronico**.
-   Facoltativo: Se si prevede che ciascun cliente in avere più mandati, in ** periodo ** sistemi, selezionare ** ** fattura. Un pagamento separato verrà creato per ogni fattura e ciascun pagamento il calcolo ordine specificato per la fattura.
-   Selezionare l'opzione **Richiedi mandato** per creare i pagamenti utilizzando i mandati di addebito diretto. L'opzione **Richiedi mandato** è disponibile solo se si seleziona **Pagamento elettronico** nel campo **Tipo di pagamento**.

Vedere anche [] panoramica dell'addebito diretto (sepa-direct-debit-overview.md) 

