---
title: Funzionalità di divisione delle fatture
description: Questo articolo descrive la configurazione della funzionalità per la divisione delle fatture in base all'indirizzo di consegna e al numero di conto imposta (TAN).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7bbeb94429c2c69b7b8ea3089390db676a021b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874434"
---
# <a name="split-invoice-functionality"></a>Funzionalità di divisione delle fatture

[!include [banner](../includes/banner.md)]

Questo articolo descrive la configurazione della funzionalità per la divisione delle fatture in base all'indirizzo di consegna e al numero di conto imposta (TAN).

Nella pagina **Parametri contabilità fornitori**, nella scheda **Generale**, seleziona la casella di controllo **Entrata prodotti** o **Fattura** per registrare e dividere un'entrata prodotti o una fattura con indirizzi di consegna e TAN diversi nella pagina **Ordine fornitore**. La fattura registrata verrà quindi divisa in base all'indirizzo di consegna e al TAN.

Nella scheda **Aggiornamento riepilogativo**, nella Scheda dettaglio **Dividi in base a**, nella riga **Informazioni consegna**, imposta l'opzione **Conferma**, **Distinta di prelievo**, **Documento di trasporto** o **Fattura** su **Sì** per registrare e suddividere una conferma, una distinta di prelievo, un documento di trasporto o una fattura in cui sono definiti indirizzi di consegna e TAN diversi per righe di fattura diverse nella pagina **Ordine cliente**. La fattura verrà quindi divisa dapprima in base all'indirizzo di consegna e quindi in base al TAN.

> [!IMPORTANT]
> - Se non ci sono opzioni di **Informazioni consegna** impostate su **Sì**, la fattura verrà registrata come singola fattura. Non si verificherà alcuna divisione di fattura.
> - Per dividere e registrare un documento di trasporto in cui le righe di fattura hanno indirizzi di consegna e TAN diversi, devi impostare l'opzione **Documento di trasporto** di **Informazioni consegna** su **Sì**.
> - Per dividere e registrare una fattura in cui le righe di fattura hanno indirizzi di consegna e TAN diversi, devi impostare l'opzione **Fattura** di **Informazioni consegna** su **Sì**.
> - Per dividere una fattura in cui le righe di fattura hanno indirizzi di consegna differenti ma lo stesso TAN, imposta l'opzione **Fattura** di **Informazioni consegna** su **No**. La fattura verrà divisa dapprima in base all'indirizzo di consegna.

## <a name="example"></a>Esempio

In questo esempio, l'opzione **Fattura** di **Informazioni consegna** è impostata su **Sì** nella scheda **Aggiornamento riepilogativo** della pagina **Parametri contabilità fornitori**. Viene registrata una fattura di acquisto con la seguente impostazione per indirizzi di consegna e TAN nelle righe:

- **Riga articolo 1:** Indirizzo di consegna 1, TAN-ABCD12345A
- **Riga articolo 2:** Indirizzo di consegna 1, TAN-ABCD12345A
- **Riga articolo 3:** Indirizzo di consegna 2, TAN-ABCE12345B
- **Riga articolo 4:** Indirizzo di consegna 3, TAN-ABCD12345A

In questo caso, la fattura originale viene divisa in due fatture e registrata nel modo seguente:

- La fattura 1 viene registrata per la riga articolo 1 e la riga articolo 2, poiché entrambe le righe hanno lo stesso indirizzo di consegna e TAN.
- La fattura 2 viene registrata per la riga articolo 3.
- La fattura 3 viene registrata per la riga articolo 4.
