---
title: Parametri interaziendali
description: Questo argomento spiega i parametri interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: face3cbd21998edcba528548ec4ae52354330aa3
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778499"
---
# <a name="intercompany-parameters"></a>Parametri interaziendali

[!include [banner](../../includes/banner.md)]

In un'organizzazione interaziendale è possibile impostare i parametri che determinano il modo in cui gestire gli scambi commerciali tra diverse persone giuridiche. Questi parametri sono determinati a loro volta dai campi selezionati ed è possibile selezionare varie combinazioni per riflettere i diversi scenari commerciali.

Nei due esempi seguenti vengono illustrati gli scenari per organizzazioni interaziendali, una con due livelli e una con tre livelli.

## <a name="example-1-two-level-intercompany-chain"></a>Esempio 1: catena interaziendale a due livelli

L'organizzazione interaziendale include le seguenti persone giuridiche:

- Persona giuridica A, che si occupa della vendita ai clienti esterni ma non dispone di scorte e che acquista dalla persona giuridica B.
- Persona giuridica B, che vende esclusivamente alla persona giuridica A.

Entrambe le persone giuridiche possono vendere e acquistare l'una dall'altra.

In questo esempio il prezzo nell'ordine cliente originario, indirizzato al cliente esterno, si basa sempre sul prezzo di vendita. Il prezzo nell'ordine cliente interaziendale e nell'ordine fornitore interaziendale viene controllato dal prezzo di vendita o di trasferimento interno nell'ordine cliente interaziendale nella persona giuridica B.

Le informazioni nell'intestazione ordine sono controllate dall'ordine cliente originario al cliente esterno. Le eventuali modifiche apportate all'ordine cliente interaziendale non verranno sincronizzate con l'ordine cliente originario.

Nella persona giuridica A, nella pagina **Interaziendale** per i fornitori, selezionare **Criteri ordine fornitore**. Selezionare i seguenti campi nel gruppo di campi **Ordine cliente originario (consegna diretta)**:

- **Stampa documento di trasporto automaticamente**
- **Registra fattura automaticamente**
- **Stampa fattura automaticamente**

Nel gruppo di campi **Ordine fornitore interaziendale (consegna diretta)**, selezionare il seguente campo:

- **Registra fattura automaticamente**

Nel gruppo **Ordine fornitore originale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**

Nel gruppo di campi **Ordine fornitore interaziendale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**
- **Numero batch**
- **Numero di serie**

Nella persona giuridica B, nella pagina **Interaziendale** per i clienti, selezionare **Criteri ordine cliente**. Selezionare i seguenti campi nel gruppo di campi **Creazione ordine cliente interaziendale**:

- **Numerazione ordine cliente** : **Società + numero originale**
- **Consenti aggiornamento riepilogativo dei documenti per cliente originario**

Nel gruppo di campi **Prezzi ordine cliente interaziendale**, selezionare i seguenti campi:

- **Ricerca prezzi e sconti**
- **Consenti modifica prezzi**
- **Consenti modifica sconti**

Nel gruppo di campi **Ordine cliente interaziendale \> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Numero batch**
- **Numero di serie**

## <a name="example-2-three-level-intercompany-chain"></a>Esempio 2: catena interaziendale a tre livelli

L'organizzazione interaziendale include le seguenti persone giuridiche:

- Persona giuridica A, che si occupa della vendita ai clienti esterni e acquista dalla persona giuridica B.
- Persona giuridica B, che non può effettuare consegne di prodotti e deve acquistare dalla persona giuridica C.
- Persona giuridica C, che effettua consegne di prodotti alla persona giuridica B.

Il prezzo di trasferimento interno tra le persone giuridiche B e C si basa sul costo dalla persona giuridica venditrice all'inizio della catena e sul costo alla persona giuridica A che vende ai clienti esterni. Il prezzo nell'ordine cliente originario al cliente esterno è tuttavia sempre basato sul prezzo di vendita.

Il prezzo in tutti gli ordini cliente interaziendali e gli ordini fornitore interaziendali viene controllato nell'ordine cliente interaziendale all'inizio della catena. Pertanto, la persona giuridica C che vende a persona giuridica B controlla il prezzo. Il prezzo nell'ordine cliente interaziendale si basa sul prezzo di vendita o di trasferimento interno impostato nella persona giuridica C.

Le informazioni nell'intestazione ordine sono controllate dall'ordine cliente originario al cliente esterno. Le eventuali modifiche apportate agli ordini interaziendali non verranno sincronizzate con l'ordine cliente originario.

Dovranno essere selezionati i seguenti parametri:

Nella persona giuridica A, nella pagina **Interaziendale** per i fornitori, selezionare **Criteri ordine fornitore**. Selezionare i seguenti campi nel gruppo di campi **Ordine cliente originario (consegna diretta)**:

- **Stampa documento di trasporto automaticamente**
- **Registra fattura automaticamente**
- **Stampa fattura automaticamente**

Nel gruppo di campi **Ordine fornitore interaziendale (consegna diretta)**, selezionare il seguente campo:

- **Registra fattura automaticamente**

Nel gruppo di campi **Ordine fornitore originale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**

Nel gruppo di campi **Ordine fornitore interaziendale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**
- **Numero batch**
- **Numero di serie**

Nella persona giuridica B, nella pagina **Interaziendale** per i clienti, selezionare **Criteri ordine cliente**. Selezionare i seguenti campi nel gruppo di campi **Creazione ordine cliente interaziendale**:

- **Numerazione ordine cliente** : **Società + numero originale**
- **Consenti aggiornamento riepilogativo dei documenti per cliente originario**

Nel gruppo di campi **Ordine cliente interaziendale \> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Numero batch**
- **Numero di serie**

Nel gruppo di campi **Registrazione fattura cliente interaziendale**, selezionare i seguenti campi:

- **Prezzo unitario uguale a prezzo di costo**
- **Inizia registrazione fattura cliente originario**

Nella persona giuridica B, nella pagina **Interaziendale** per i fornitori, selezionare **Criteri ordine fornitore**. Selezionare i seguenti campi nel gruppo di campi **Ordine cliente originario (consegna diretta)**:

- **Stampa documento di trasporto automaticamente**
- **Registra fattura automaticamente**
- **Stampa fattura automaticamente**

Nel gruppo di campi **Ordine fornitore interaziendale (consegna diretta)**, selezionare il seguente campo:

- **Registra fattura automaticamente**

Nel gruppo di campi **Ordine fornitore originale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**
- **Prezzo e sconto**

Nel gruppo di campi **Ordine fornitore interaziendale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Informazioni cliente**
- **Numero RMA**
- **Numero batch**
- **Numero di serie**

Nella persona giuridica C, nella pagina **Interaziendale** per i clienti, selezionare **Criteri ordine cliente**. Selezionare i seguenti campi nel gruppo di campi **Creazione ordine cliente interaziendale**:

- **Numerazione ordine cliente** : **Codice sequenza numerica**
- **Consenti aggiornamento riepilogativo dei documenti per cliente originario**

Nel gruppo di campi **Prezzi ordine cliente interaziendale**, selezionare il seguente campo:

- **Ricerca prezzi e sconti**

Nel gruppo di campi **Registrazione fattura cliente interaziendale**, selezionare i seguenti campi:

- **Prezzo unitario uguale a prezzo di costo**
- **Inizia registrazione fattura cliente originario**

Nel gruppo di campi **Ordine cliente interaziendale <-> Ordine fornitore interaziendale**, selezionare i seguenti campi:

- **Numero batch**
- **Numero di serie**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
