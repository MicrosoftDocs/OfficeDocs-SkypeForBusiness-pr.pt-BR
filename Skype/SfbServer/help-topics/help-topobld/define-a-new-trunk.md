---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:'
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218552"
---
# <a name="define-a-new-trunk"></a>Definir um Novo Tronco

Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:

- **Nome do tronco**: nome exclusivo em sua topologia que identificará esse tronco

- **Gateway PSTN Associado**: selecione na lista um gateway PSTN implantado e configurado em sua implantação

- **Porta de escuta para o gateway IP/PSTN**: porta na qual o gateway IP-PBX ou PSTN escutará. Precisa ser exclusiva, diferente de todas as outras portas de escuta de tronco configuradas em sua implantação

- **Protocolo de Transporte SIP**: selecione na lista TCP ou TLS.

- **Servidor de mediação associado**: selecione na lista um servidor de mediação que é implantado e configurado em sua implantação

- **Porta do servidor de mediação associado**: defina o valor da porta como igual ao valor da porta TCP ou TLS do servidor de mediação que esse tronco SIP usará

## <a name="see-also"></a>Confira também

[Tronco M:N no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Como faço para implementar o tronco SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
