---
title: Adicionar Opções de Servidor de Borda
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 'Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda dá suporte a usuários remotos em sua organização que se insere fora do firewall usando uma VPN (rede virtual privada). Você também tem as seguintes opções de recurso de pool de borda:'
ms.openlocfilehash: 9ac07d7a15e138c3fe817aab6754ca098f8ff774
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834479"
---
# <a name="add-edge-server-options"></a>Adicionar Opções de Servidor de Borda

Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda dá suporte a usuários remotos em sua organização que se insere fora do firewall usando uma VPN (rede virtual privada). Você também tem as seguintes opções de recurso de pool de borda:

- Uso de um único nome de domínio totalmente qualificado (FQDN) e endereço IP para todos os serviços de borda, incluindo o serviço de Borda de Acesso, o serviço de Borda de WebConferência e o serviço de Borda A/V. Se você não selecionar a opção de usar um único FQDN e um endereço IP, precisará especificar um FQDN e um endereço IP separados para cada um desses três serviços de Borda como parte do processo de implantação. Para obter detalhes sobre os serviços de Borda, consulte [Components Required for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access) na documentação planejamento.

    > [!NOTE]
    > Se você selecionar essa opção, deverá especificar um número de porta diferente para cada um dos serviços de Borda (configurações de porta padrão recomendadas: 444 para serviço de Borda de Acesso, 8057 para serviço de Borda de WebConferência e 443 para serviço de Borda A/V). Selecionar essa opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode inserir um FQDN usado para todos os três serviços.

- Suporte para federação. Selecione essa opção se quiser dar suporte à comunicação entre usuários internos e usuários em domínios confiáveis fora da sua organização, incluindo todos os usuários de um provedor de mensagens instantâneas públicas (IM) com suporte. Se você selecionar essa opção, precisará configurar o suporte para domínios federados específicos e provedores de serviços de conectividade de IM públicos que você deseja dar suporte. Para obter detalhes sobre como configurar o suporte para federação e outros tipos de acesso de usuário externo, consulte [Configuring Support for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access) na documentação de Implantação do Servidor de Borda.

    > [!NOTE]
    > Somente um pool de Front-End ou Servidor de Borda Padrão em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo usuários de IM públicas, passa pelo mesmo pool de Borda ou servidor de borda único. Por exemplo, se sua implantação inclui um pool de Borda ou único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.

- Habilitar a federação XMPP. Selecione essa opção se quiser dar suporte à comunicação entre usuários internos e parceiros XMPP confiáveis.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como incluir Servidores de Borda na topologia existente, consulte  [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology), na documentação de Implantação do Servidor de Borda.