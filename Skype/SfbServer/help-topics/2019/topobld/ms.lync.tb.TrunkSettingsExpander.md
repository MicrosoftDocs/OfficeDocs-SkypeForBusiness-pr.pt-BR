---
title: Expansor de Configurações de Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:'
ms.openlocfilehash: 97c1578418fdf46ad39256312d7aa15abd44ff84
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797402"
---
# <a name="trunk-settings-expander"></a>Expansor de Configurações de Tronco

Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:

 **Nome do tronco** é uma entrada necessária e identifica exclusivamente o tronco SIP na implantação.

 **Gateway PSTN associado**: selecione um gateway PSTN existente definido na implantação.

 **Porta de escuta para gateway IP/PSTN**: indica em qual porta TCP/IP o gateway escutará as solicitações. O valor necessário pode variar com base no fornecedor do gateway, mas o padrão é a porta 5067.

 **Protocolo de Transporte SIP**: protocolo usado pode ser TCP ou TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o suporte incluído no seu gateway. Como o padrão é TLS, ele deve ser considerado a seleção mais segura, caso o gateway ofereça suporte para TLS.

 **Servidor de mediação associado**: selecione um servidor de mediação existente na implantação para associá-lo ao tronco SIP.

> [!NOTE]
> Somente o tronco raiz podem ser associados a um servidor de mediação.

 **Porta do servidor de mediação associada**: um valor obrigatório; isso é definido como o valor que o servidor de mediação está configurado para escuta.

![Expansor de Configurações de Tronco](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Confira também

[Lista de verificação de implantação de entroncamento SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componentes e topologias para entroncamento SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
