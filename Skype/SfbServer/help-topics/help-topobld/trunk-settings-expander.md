---
title: Expansor de Configurações de Tronco
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a>Expansor de configurações de tronco
 
Para editar ou modificar as configurações de um tronco SIP, faça o seguinte:
  
 **Nome do tronco** é uma entrada necessária e identifica exclusivamente o tronco SIP na implantação.
  
 **Gateway PSTN associado**: selecione um gateway PSTN existente definido na implantação.
  
 **Porta de escuta para gateway IP/PSTN**: indica em qual porta TCP/IP o gateway escutará as solicitações. O valor necessário pode variar com base no fornecedor do gateway, mas o padrão é a porta 5067.
  
 **Protocolo de Transporte SIP**: protocolo usado pode ser TCP ou TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o suporte incluído no seu gateway. Como o padrão é TLS, ele deve ser considerado a seleção mais segura, caso o gateway ofereça suporte para TLS.
  
 **Servidor de mediação associado**: selecione um servidor de mediação existente na implantação para associá-lo ao tronco SIP.
  
> [!NOTE]
> Somente o tronco raiz pode ser associado um Lync Server 2010 ou o servidor de mediação do Lync Server 2013. 
  
 **Porta do servidor de mediação associado**: um valor necessário, definido como o valor que o servidor de mediação é configurado para escutar em.
  
![Expansor de configurações de tronco](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>Consulte também

#### 

[Lista de verificação de implantação de troncos SIP](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[Componentes e topologias para tronco SIP](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

