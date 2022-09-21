---
title: Funzioni di prezzo in POS
description: Questo articolo descrive varie funzioni di prezzo e sconto nell'applicazione POS di Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473689"
---
# <a name="pricing-functions-in-pos"></a>Funzioni di prezzo in POS

[!include [banner](includes/banner.md)]

Questo articolo descrive varie funzioni di prezzo e sconto nell'applicazione POS di Microsoft Dynamics 365 Commerce.

L'applicazione POS di Dynamics 365 Commerce offre funzionalità avanzate che consentono ai lavoratori di prima linea di eseguire operazioni di Store Commerce. La tabella seguente mostra le funzioni di prezzo e sconto attualmente disponibili nell'applicazione.

| Funzione                       | Operazioni POS |
|--------------------------------|----------------|
| Visualizza prezzi                    | [Controllo del prezzo](#price-check) |
| Visualizza sconti                 | [Visualizza tutti gli sconti](#view-all-discounts)<br>[Visualizza sconti disponibili](#view-available-discounts) |
| Forza prezzi                | [Forzatura prezzo](#price-override) |
| Applica o rimuovi sconti      | [Importo sconto riga](#line-discount-amount)<br>[Percentuale sconto riga](#line-discount-percent)<br>[Totale importo sconto](#total-discount-amount)<br>[Percentuale sconto totale](#total-discount-percent)<br>[Rimuovi sconti di sistema da transazione](#remove-system-discounts-from-transaction)<br>[Riapplica sconti di sistema](#reapply-system-discounts) |
| Applica o rimuovi buoni sconto        | [Aggiungi codice buono sconto](#add-coupon-code)<br>[Rimuovi codice buono sconto](#remove-coupon-code) |
| Calcola prezzi e sconti | [Ricalcola](#recalculate) |

Per informazioni su come configurare le operazioni precedenti nell'applicazione POS e se queste supportano la modalità offline, vedi [Operazioni POS online e offline](pos-operations.md).

## <a name="price-check"></a>Controllo del prezzo

L'operazione **Controllo del prezzo** consente agli utenti POS di cercare prezzi preconfigurati per un prodotto specifico.

## <a name="view-all-discounts"></a>Visualizza tutti gli sconti

L'operazione **Visualizza tutti gli sconti** consente agli utenti POS di cercare tutte le promozioni effettive attualmente in vigore nel punto vendita. Nello specifico, questa operazione elenca tutti gli sconti che soddisfano una qualsiasi delle seguenti condizioni:

- Il gruppo di prezzi dello sconto corrisponde al gruppo di prezzi del negozio.
- Il gruppo di prezzi dello sconto è associato a un programma di affiliazione o fedeltà.
- Il gruppo di prezzi dello sconto è associato a un catalogo collegato al negozio.

L'operazione **Visualizza tutti gli sconti** mostra solo gli sconti che non competono con nessuno degli sconti già applicati. Questo comportamento aiuta a garantire che, se un addetto alle vendite informa un cliente di uno sconto e il cliente intraprende l'azione richiesta (ad esempio, il cliente acquista un altro articolo per ottenere uno sconto del 10%), lo sconto viene applicato alla transazione. Gli sconti basati su buono sconto vengono visualizzati solo quando il parametro **Applica senza buono sconto** è attivato.

Nell'ambito dell'operazione **Visualizza tutti gli sconti**, gli utenti POS possono cercare sconti per nome e descrizione e possono filtrare gli sconti a seconda che richiedano o meno un buono sconto.

## <a name="view-available-discounts"></a>Visualizza sconti disponibili

L'operazione **Visualizza sconti disponibili** consente agli utenti POS di visualizzare tutti gli sconti applicabili a una riga selezionata in una transazione o all'intera transazione. Gli sconti applicabili a una riga selezionata includono sconti già applicati e sconti non ancora applicati che possono essere applicati (ad esempio, sconti gamma che richiedono articoli aggiuntivi). Se uno sconto applicabile è collegato a un buono sconto in cui il parametro **Applica senza codice buono sconto** è attivato, l'utente POS può anche utilizzare la funzione **Applica buono sconto** durante questa operazione per usare il buono sconto direttamente, senza dover immettere o scansionare codici buono sconto o codici a barre buono sconto.

## <a name="price-override"></a>Forzatura prezzo

L'operazione **Forzatura prezzo** consente agli utenti POS di sostituire il prezzo di vendita di un prodotto in una transazione. Questa operazione funziona solo per i prodotti configurati per consentire la sostituzione del prezzo.

## <a name="line-discount-amount"></a>Importo sconto riga

L'operazione **Importo sconto riga** consente agli utenti POS di immettere l'importo di uno sconto per una voce in una transazione. Questa operazione si applica solo agli articoli scontabili e rispetta il valore **Importo sconto riga massimo** specificato nel gruppo di autorizzazioni POS per l'utente.

## <a name="line-discount-percent"></a>Percentuale sconto riga

L'operazione **Percentuale sconto riga** consente agli utenti POS di immettere una percentuale di sconto per una voce in una transazione. Questa operazione si applica solo agli articoli scontabili e rispetta il valore **Percentuale di sconto riga massima** specificato nel gruppo di autorizzazioni POS per l'utente.

## <a name="total-discount-amount"></a>Importo sconto totale

L'operazione **Importo sconto totale** consente agli utenti POS di immettere l'importo di uno sconto per una transazione. Questa operazione si applica solo agli articoli scontabili e rispetta il valore **Importo sconto totale massimo** specificato nel gruppo di autorizzazioni POS per l'utente. Se l'importo dello sconto immesso supera l'importo totale massimo dello sconto, l'operazione viene bloccata e non viene attivato alcun flusso di sostituzione delle autorizzazioni. Al momento, non è possibile applicare un importo totale di sconto a un carrello con articoli di vendita e articoli di reso.

## <a name="total-discount-percent"></a>Percentuale sconto totale

L'operazione **Percentuale sconto totale** consente agli utenti POS di immettere la percentuale di sconto per una transazione. Questa operazione si applica solo agli articoli scontabili e rispetta il valore **Percentuale di sconto totale massima** specificato nel gruppo di autorizzazioni POS per l'utente. Se la percentuale di sconto immessa supera la percentuale di sconto totale massima, l'operazione viene bloccata e non viene attivato alcun flusso di sostituzione delle autorizzazioni. Al momento, non è possibile applicare una percentuale di sconto totale a un carrello con articoli di vendita e articoli di reso.

## <a name="remove-system-discounts-from-transaction"></a>Rimuovi sconti di sistema da transazione

L'operazione **Rimuovi sconti di sistema da transazione** consente agli utenti POS di rimuovere tutti gli sconti di sistema applicati (inclusi gli sconti basati su buono sconto) da una transazione. Dopo l'esecuzione di questa operazione, il motore di determinazione dei prezzi inizia a escludere gli sconti di sistema dall'ambito di calcolo dello sconto. L'operazione **Rimuovi sconti di sistema da transazione** non rimuove gli sconti manuali.

## <a name="reapply-system-discounts"></a>Riapplica sconti di sistema

L'operazione **Riapplica sconti di sistema** consente agli utenti POS di riapplicare gli sconti calcolati dal sistema a una transazione se gli sconti sono stati rimossi utilizzando l'operazione **Rimuovi sconti di sistema da transazione**. Dopo l'esecuzione di questa operazione, il motore di determinazione dei prezzi inizia a includere gli sconti di sistema nell'ambito di calcolo dello sconto.

## <a name="add-coupon-code"></a>Aggiungi codice buono sconto

L'operazione **Aggiungi codice buono sconto** consente agli utenti POS di aggiungere un buono sconto a una transazione immettendo un codice buono sconto. In alternativa, gli utenti POS possono eseguire la scansione del codice a barre del buono sconto o immetterlo utilizzando la tastiera numerica nella schermata **Transazioni**.

## <a name="remove-coupon-code"></a>Rimuovi codice buono sconto

L'operazione **Rimuovi codice buono sconto** consente agli utenti POS di selezionare e rimuovere uno o più buoni sconto attualmente applicati a una transazione.

## <a name="recalculate"></a>Ricalcola

L'operazione **Ricalcola** consente agli utenti POS di attivare il calcolo dei prezzi su richiesta. Questa operazione è necessaria quando è abilitato il blocco del prezzo e/o il calcolo differito del prezzo e l'utente POS vuole ricalcolare i prezzi e gli sconti dopo le modifiche al carrello o all'ordine. L'operazione **Ricalcola** ricalcola sempre l'intero ordine. Non può essere utilizzata per ricalcolare le righe di vendita selezionate. Per applicare sconti manuali a una riga di vendita bloccata in POS, gli utenti POS devono prima utilizzare l'operazione **Ricalcola** per sbloccare tutte le righe di vendita.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
