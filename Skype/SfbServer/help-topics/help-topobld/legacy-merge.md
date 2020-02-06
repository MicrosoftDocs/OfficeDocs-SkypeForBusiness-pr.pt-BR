---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo da webconferência permite que usuários externos ingressem em reuniões locais. Digite o nome de domínio totalmente qualificado (FQDN) da interface externa da webconferência do servidor de borda herdado.
ms.openlocfilehash: 19e508bdaaf44f64b3d907070d96a3691ce611c0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819683"
---
# <a name="legacy-merge"></a>Mesclagem Herdada

O **FQDN externo da webconferência** permite que usuários externos ingressem em reuniões locais. Digite o nome de domínio totalmente qualificado (FQDN) da interface externa da webconferência do servidor de borda herdado.

O valor da **porta externa da conferência da Web externa** do **443** é a porta do protocolo de controle de transmissão (TCP) de protocolo de controle de transmissão (SIP) padrão configurada para clientes de conferência. Se o valor padrão não for usado, atualize o valor de **porta externa da webconferência externa** .

Marque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de im pública** se você planeja usar esse servidor de borda para Federação. Se você tiver vários servidores de Borda implantados, apenas um deles será habilitado para Federação. Se você não marcar esta caixa e decidir mais tarde de que deseja habilitar a Federação, você deve executar o assistente de mesclagem do construtor de topologia novamente, bem como publicar sua topologia. Para obter detalhes, consulte [fase 4: mesclar topologias](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


