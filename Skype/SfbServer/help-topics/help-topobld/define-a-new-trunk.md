---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:'
ms.openlocfilehash: 963a622ed2a7f3c39dca0be5199126ffaf201314
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416694"
---
# <a name="define-a-new-trunk"></a>Definir um Novo Tronco

Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:

- **Nome do tronco**: nome exclusivo em sua topologia que identificará esse tronco

- **Gateway PSTN Associado**: selecione na lista um gateway PSTN implantado e configurado em sua implantação

- **Porta de escuta para o gateway IP/PSTN**: porta na qual o gateway IP-PBX ou PSTN escutará. Precisa ser exclusiva, diferente de todas as outras portas de escuta de tronco configuradas em sua implantação

- **Protocolo de Transporte SIP**: selecione na lista TCP ou TLS.

- **Servidor de Mediação Associado**: selecione na lista um Servidor de Mediação implantado e configurado em sua implantação

- **Porta do Servidor de Mediação** Associada: defina o valor da porta igual ao valor da porta TCP ou TLS do Servidor de Mediação que este tronco SIP usará

## <a name="see-also"></a>Confira também

[Tronco M:N no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Como implementar tronco SIP?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)