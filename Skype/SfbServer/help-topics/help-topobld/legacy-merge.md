---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo de webconferência permite que usuários externos para participar de reuniões no local. Insira o nome de domínio totalmente qualificado (FQDN) da interface externa de conferência da web do servidor de borda herdado.
ms.openlocfilehash: b67ea667f2b354f7981d3bc289e63b0cf8b4e704
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888573"
---
# <a name="legacy-merge"></a>Mesclagem Herdada

O **FQDN externo de webconferência** permite que usuários externos para participar de reuniões no local. Insira o nome de domínio totalmente qualificado (FQDN) da interface externa de conferência da web do servidor de borda herdado.

O valor de **porta externa de conferência da Web externa** **443** é a porta de protocolo de controle de transmissão (TCP) Session Initiation Protocol (SIP) do padrão configurada para clientes de conferência. Se o valor padrão não foi usado, atualize o valor de **porta externa de conferência da Web externos** .

Se você planeja usar este servidor de borda para federação, marque a caixa de seleção **borda deste pool é usado para federação e conectividade de IM pública** . Se você tiver vários servidores de borda implantado, somente um deles será habilitado para federação. Se você não marcar essa caixa e você decidir, posteriormente, que você deseja habilitar a federação, você deve executar novamente o Assistente de mesclagem do construtor de topologia, bem como publicar sua topologia. Para obter detalhes, consulte [fase 4: mesclar topologias](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


