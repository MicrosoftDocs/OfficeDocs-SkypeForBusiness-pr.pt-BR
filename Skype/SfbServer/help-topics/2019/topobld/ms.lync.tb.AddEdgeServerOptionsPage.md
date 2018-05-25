---
title: Adicionar Opções de Servidor de Borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda inclui suporte para usuários remotos em sua organização que fazem logon de fora do firewall usando uma rede virtual privada (VPN). Também há as seguintes opções de recurso do pool de Borda:'
ms.openlocfilehash: c2c73a664e15a48fd0fae3282e987b5e9b2954e3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="add-edge-server-options"></a>Adicionar Opções de Servidor de Borda
 
Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda inclui suporte para usuários remotos em sua organização que fazem logon de fora do firewall usando uma rede virtual privada (VPN). Também há as seguintes opções de recurso do pool de Borda: 
  
- Uso de um único nome de domínio totalmente qualificado (FQDN) e endereço IP de todos os serviços de borda, incluindo o Serviço de Borda de Acesso, o Serviço de Borda de Webconferência e o Serviço Borda A/V. Se você não selecionar a opção para usar um único FQDN e endereço IP, será necessário especificar um FQDN e endereço IP separados para cada um dos três serviços de Borda, como parte do processo de implantação. Para obter detalhes sobre os serviços de borda, consulte [componentes necessários for External User Access](http://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) na documentação de planejamento.
    
    > [!NOTE]
    > Se você selecionar essa opção, deverá especificar um número de porta diferente para cada um dos serviços de Borda (configurações de porta padrão recomendadas: 444 para o serviço de Borda de Acesso, 8057 parra o Serviço de Borda de Webconferência e 443 para o Serviço de Borda A/V). Selecionar essa opção pode ajudar a impedir possíveis problemas de conectividade, além de simplificar a configuração, pois assim é possível inserir um FQDN usado para todos os três serviços. 
  
- Suporte para federação. Selecione essa opção para oferecer suporte à comunicação entre os usuários internos e os usuários em domínios confiáveis fora de sua organização, incluindo o suporte a quaisquer usuários de provedores de serviços públicos de mensagens instantâneas (IM). Se você selecionar essa opção, será necessário configurar o suporte aos domínios federados específicos e provedores de serviço de conectividade a redes públicas de mensagens instantâneas que você deseja incluir. Para obter detalhes sobre como configurar o suporte para federação e outros tipos de acesso de usuário externo, consulte [Configurando Support for External User Access](http://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) na documentação de implantação de servidor de borda.
    
    > [!NOTE]
    > Somente um pool de Front-Ends ou Servidor de Borda Padrão em sua organização pode ser publicado externamente para federação. Todo acesso por parte de usuários federados, incluindo usuários de redes públicas de IM, passam pelo mesmo pool de Bordas ou Servidor de Borda único. Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e outro implantado em Londres e você habilitar o suporte para federação no pool de Borda de Nova York ou único Servidor de Borda, o tráfego do sinal para usuários federados passará pelo pool de Borda ou único Servidor de Borda de Nova York. Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V. 
  
- Habilitar federação XMPP. Selecione esta opção se quiser oferecer suporte à comunicação entre usuários internos e parceiros confiáveis XMPP.
    
É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar servidores de borda a uma topologia existente, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de implantação de servidor de borda.
  

