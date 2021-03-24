---
title: Expansor de Configurações de Tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:'
ms.openlocfilehash: 5859686a6fedf8c4da15ada5c4ad92f47c24b756
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114137"
---
# <a name="trunk-settings-expander"></a>Expansor de Configurações de Tronco

Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:

 **Nome do tronco** é uma entrada necessária e identifica exclusivamente o tronco SIP na implantação.

 **Gateway PSTN associado**: selecione um gateway PSTN existente definido na implantação.

 **Porta de escuta para o gateway IP/PSTN**: Indica em qual porta TCP/IP o gateway escutará as solicitações. O valor necessário pode variar com base no fornecedor do gateway, mas o padrão é a porta 5067.

 **Protocolo de Transporte SIP**: o protocolo usado pode ser TCP ou TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o que seu gateway suporta. O padrão é TLS, e deve ser considerado a seleção mais segura, se o gateway suportar TLS.

 **Servidor de Mediação Associado**: Selecione um Servidor de Mediação existente na implantação para associar ao tronco SIP.

> [!NOTE]
> Somente o tronco raiz pode ser associado a um Lync Server 2010 ou Lync Server 2013 Mediation Server.

 **Porta do Servidor de Mediação** Associada : Um valor obrigatório, que é definido como o valor no que o Servidor de Mediação está configurado para ouvir.

![Expansor de Configurações de Tronco](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Confira também

[Lista de verificação de implantação de tronco SIP](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Componentes e topologias para tronco SIP](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)