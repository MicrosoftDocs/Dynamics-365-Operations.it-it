---
title: Pagamenti IVA e regole di arrotondamento
description: Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adc48d1841903670577684b1c3d773d323c19ea1
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275676"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Pagamenti IVA e regole di arrotondamento

[!include [banner](../includes/banner.md)]

Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.

Periodicamente, l'IVA deve essere dichiarata e pagata agli uffici tributari. Questa operazione può essere effettuata mediante l'esecuzione del processo di liquidazione e registrazione IVA nella pagina IVA. L'IVA per un periodo verrà liquidata nei conti IVA e il saldo IVA verrà registrato nel conto di liquidazione IVA. Il saldo IVA, registrato nel conto di liquidazione IVA, può essere arrotondato in base a quanto richiesto dagli uffici tributari impostando una regola di arrotondamento nella pagina IVA. 

La differenza di arrotondamento viene registrata nel conto di arrotondamento IVA selezionato nel campo Conti per transazioni automatiche nella contabilità generale.

Nell'esempio seguente viene illustrato il funzionamento della regola di arrotondamento IVA.

## <a name="examples"></a>Esempi

L'IVA totale per un periodo mostra un saldo in avere di -98.765,43. La persona giuridica dispone più prelievo IVA superiore a quanto ha pagato. Di conseguenza, la persona giuridica deve denaro all'ufficio tributario. 

La persona giuridica desidera utilizzare un metodo che consenta di arrotondare il saldo all'unità più vicina. L'utente responsabile della contabilità IVA esegue le seguenti operazioni.

1. Fare click su **Imposte** > **Imposte indirette** > **IVA** > **Uffici IVA**.
2. Nella scheda dettaglio **Generale**, nel campo **Tipo di arrotondamento** selezionare **Normale**.
3. Nel campo **Arrotondamento**, immettere 1,00.
4. Quando è il momento di pagare le imposte sulle vendite all'autorità fiscale, andare a **Tasse** > **Dichiarazioni** > **IVA** > **Liquida e registra IVA**. Nel conti di liquidazione IVA, è possibile notare che l'importo di soggettività tributaria di **98.765,43** viene arrotondato a **98.765**.

Le seguente tabella mostra un importo di 98.765,43 arrotondato utilizzando ogni metodo di arrotondamento disponibile nel campo **Tipo di arrotondamento** nella pagina **Uffici IVA**.

> [!NOTE]                                                                                  
> Se il valore di arrotondamento è impostato su 0,00:
>
> - Per l'arrotondamento normale, il comportamento dell'arrotondamento è lo stesso di **Arrotondamento = 0,01**.
> - Per **Opzioni Tipo di arrotondamento**, **Arrotondamento per difetto**, **Arrotondamento per eccesso** e **A proprio vantaggio**, il comportamento è lo stesso di **Arrotondamento = 1,00**.

| Opzione Tipo di arrotondamento                | Valore arrotondamento = 0,01 | Valore arrotondamento = 0,10 | Valore arrotondamento = 1,00 | Valore arrotondamento = 100,00 | Valore arrotondamento = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normale                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| Arrotondamento per difetto                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Arrotondamento per eccesso                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| A proprio vantaggio, per un saldo in avere | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| A proprio vantaggio, per un saldo in dare  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Arrotondamento normale e la precisione dell'arrotondamento è 0.01

<table>
  <tr>
    <td>Arrotondamento
    </td>
    <td>Processo di calcolo
    </td>
  </tr>
    <tr>
    <td>round(1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>round(1,015 / 0,01, 0) = round(101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>round(1,014 / 0,01, 0) = round(101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>round(1,011 / 0,02, 0) = round(50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>round(1,009 / 0,02, 0) = round(50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Se si seleziona A proprio vantaggio, l'arrotondamento è sempre a vantaggio della persona giuridica. 

Per ulteriori informazioni, vedere i seguenti argomenti:
- [Panoramica dell'IVA](indirect-taxes-overview.md)
- [Creare un pagamento IVA](tasks/create-sales-tax-payment.md)
- [Creare transazioni IVA in documenti](tasks/create-sales-tax-transactions-documents.md)
- [Visualizzare transazioni IVA registrate](tasks/view-posted-sales-tax-transactions.md)
- [Funzione di arrotondamento](https://msdn.microsoft.com/library/aa850656.aspx)


