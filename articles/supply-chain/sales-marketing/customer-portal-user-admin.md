---
title: Creare e gestire utenti del portale clienti
description: Questo argomento spiega come creare account utente del portale clienti e impostare le relative autorizzazioni.
author: dasani-madipalli
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 38b479a72ce6d9446e04b14ed939b63d41d3b94b299f195974a84ca7c8ad0d65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763989"
---
# <a name="create-and-manage-customer-portal-users"></a>Creare e gestire utenti del portale clienti

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Nell'implementazione predefinita, gli utenti non possono autoregistrarsi per i siti Web creati utilizzando il portale clienti. Per accedere e utilizzare un sito Web, gli utenti devono essere invitati dall'amministratore. Microsoft ha intenzionalmente bloccato la funzionalità che consente agli utenti di autoregistrarsi.

Affinché un utente possa utilizzare un sito Web, è necessario creare un record di contatto per quell'utente. Questo record indica a quale account cliente e a quale persona giuridica appartiene l'utente. Queste informazioni sono essenziali per garantire che l'utente possa creare e visualizzare ordini cliente.

Quando gli utenti si autoregistrano, i relativi record di contatto vengono creati automaticamente. Pertanto, non è possibile garantire che un utente selezioni l'account cliente e la persona giuridica corretti. D'altra parte, il processo di invito consente a un amministratore di assegnare l'account cliente e la persona giuridica corretti al record di contatto prima di inviare un invito. Se si intende personalizzare la soluzione di modo che gli utenti possano autoregistrarsi, considerare le possibili conseguenze.

## <a name="video"></a>Video 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

Il video su come [invitare i clienti a registrarsi e utilizzare il portale per i clienti](https://youtu.be/drGUYHX9QIQ) (mostrato in precedenza) è incluso nella [playlist di Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="prerequisite-setup"></a>Configurazione dei prerequisiti

I contatti nei portali Power Apps sono memorizzati come record nella tabella **Contatti** in Microsoft Dataverse. La doppia scrittura quindi sincronizza questi record con Microsoft Dynamics 365 Supply Chain Management come necessario.

![Diagramma di sistema per i contatti del portale clienti.](media/customer-portal-contacts.png "Diagramma di sistema per i contatti del portale clienti")

Prima di iniziare a invitare nuovi clienti, assicurarsi di aver abilitato il mapping della tabella **Contatto** in doppia scrittura.

## <a name="the-invitation-process"></a>Processo di invito

Per invitare un contatto esistente nel portale clienti, seguire i passaggi in [Invitare contatti nei propri portali](/powerapps/maker/portals/configure/invite-contacts) nella documentazione sui portali Power Apps.

Prima di invitare un cliente a iscriversi al portale clienti, assicurarsi che il [record di contatto](/powerapps/maker/portals/configure/configure-contacts) del cliente sia disponibile e configurato nel modo seguente:

1. Impostare il campo **Società** sulla persona giuridica a cui il cliente deve appartenere in Supply Chain Management.
2. Impostare il campo **Numero account** sul numero di account cliente che l'utente deve avere in Supply Chain Management.

Dopo aver creato un contatto, questo dovrebbe essere visibile in Supply Chain Management.

Per ulteriori informazioni, vedere [Configurare un contatto per l'uso in un portale](/powerapps/maker/portals/configure/configure-contacts) nella documentazione sui portali Power Apps.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Ruoli Web e autorizzazioni di tabella predefiniti

I ruoli utente nei portali Power Apps sono definiti mediante [ruoli Web ](/powerapps/maker/portals/configure/create-web-roles) e [autorizzazioni di tabella](/powerapps/maker/portals/configure/assign-entity-permissions). Alcuni ruoli sono definiti per il portale clienti predefinito. È possibile creare nuovi ruoli e modificare o rimuovere ruoli esistenti.

### <a name="out-of-box-web-roles"></a>Ruoli Web predefiniti

Questa sezione descrive i ruoli Web forniti con il portale clienti.

Per ulteriori informazioni su come modificare i ruoli utente predefiniti, vedere [Creare ruoli Web per portali](/powerapps/maker/portals/configure/create-web-roles) e [Aggiungere sicurezza basata su record utilizzando autorizzazioni di tabella per portali](/powerapps/maker/portals/configure/assign-entity-permissions) nella documentazione sui portali Power Apps.

#### <a name="administrator"></a>Amministratore

L'amministratore supervisiona e gestisce il sito Web. Questa persona eseguirà il provisioning del portale clienti e lo configurerà. L'amministratore gestisce gli aspetti IT e di sicurezza del portale e si assicura che tutto funzioni senza intoppi. L'amministratore può anche personalizzare e/o modificare il portale aggiungendo nuove funzionalità, creando nuovi ruoli ed eseguendo altre operazioni.

#### <a name="customer-representative"></a>Rappresentante clienti

Un rappresentante clienti lavora per un'azienda cliente ed è responsabile della gestione degli ordini effettuati dall'azienda. Il rappresentante del cliente può visualizzare tutti gli ordini eseguiti per l'azienda e gli utenti che li hanno effettuati. Inoltre, può visualizzare informazioni sull'account globale e i contatti che possono effettuare ordini per conto di tale account.

#### <a name="authorized-users"></a>Utenti autorizzati

Gli utenti autorizzati possono effettuare ordini e visualizzare lo stato degli ordini che hanno effettuato. Tuttavia, non possono visualizzare lo stato degli ordini effettuati da altri utenti nell'azienda.

#### <a name="unauthorized-users"></a>Utenti non autorizzati

Gli utenti non autorizzati non possono visualizzare alcun dato. Possono visualizzare solo informazioni pubbliche, come termini e condizioni, e dettagli sulla società che gestisce il portale clienti.

#### <a name="example"></a>Esempio

La tabella seguente mostra quali ordini cliente sono visibili agli utenti per ciascun ruolo Web nel sistema.

| Ordine cliente | Amministratore | Rappresentante del cliente&nbsp;X | Utente autorizzato: Jane | Utente autorizzato: Sam | Utente non autorizzato: May |
|---|---|---|---|---|---|
| Autore ordine cliente&nbsp;X: &nbsp;Jane | Sì | Sì | Sì | Nessuna | Nessuna |
| Autore ordine cliente&nbsp;X: &nbsp;Sam | Sì | Sì | Nessuna | Sì | Nessuna |
| Autore cliente&nbsp;Y: &nbsp;May | Sì | Nessuna | Nessuna | Nessuna | Nessuna |

> [!NOTE]
> Anche se Sam e Jane sono contatti che lavorano per il cliente X, possono vedere solo gli ordini che essi stessi hanno effettuato e nient'altro. Sebbene May abbia un ordine nel sistema, non può vederlo nel portale clienti, poiché è un utente non autorizzato. Inoltre, deve aver effettuato l'ordine attraverso un canale diverso dal portale clienti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]