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
ms.openlocfilehash: 827399a74f2af29645d77f28efe9b7f2fc5fb3ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818012"
---
# <a name="trunk-settings-expander"></a>Expansor de Configurações de Tronco

Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:

 **Nome do tronco** é uma entrada necessária e identifica exclusivamente o tronco SIP na implantação.

 **Gateway PSTN associado**: selecione um gateway PSTN existente definido na implantação.

 **Porta de escuta para o gateway IP/PSTN**: Indica em qual porta TCP/IP o gateway escutará as solicitações. O valor necessário pode variar com base no fornecedor do gateway, mas o padrão é a porta 5067.

 **Protocolo de Transporte SIP**: o protocolo usado pode ser TCP ou TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o que seu gateway suporta. O padrão é TLS, e deve ser considerado a seleção mais segura, se o gateway suportar TLS.

 **Servidor de Mediação Associado:** selecione um Servidor de Mediação existente na implantação para associar ao tronco SIP.

> [!NOTE]
> Somente o tronco raiz pode ser associado a um Servidor de Mediação do Lync Server 2010 ou do Lync Server 2013.

 **Porta do Servidor de Mediação** Associada: um valor obrigatório, é definido como o valor que o Servidor de Mediação está configurado para escutar.

![Expansor de Configurações de Tronco](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Confira também

[Lista de verificação de implantação de tronco SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componentes e topologias para tronco SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
