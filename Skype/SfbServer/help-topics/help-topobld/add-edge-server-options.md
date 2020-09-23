---
title: Adicionar Opções de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Selecione cada recurso que você deseja habilitar para o pool de borda. Por padrão, o pool de borda oferece suporte a usuários remotos em sua organização que entram de fora do firewall usando uma rede virtual privada (VPN). Você também tem as seguintes opções de recurso do pool de borda:'
ms.openlocfilehash: dfcaafce36d525b676a606db4f164dfdd05f26ba
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216562"
---
# <a name="add-edge-server-options"></a>Adicionar Opções de Servidor de Borda

Selecione cada recurso que você deseja habilitar para o pool de borda. Por padrão, o pool de borda oferece suporte a usuários remotos em sua organização que entram de fora do firewall usando uma rede virtual privada (VPN). Você também tem as seguintes opções de recurso do pool de borda:

- Uso de um único FQDN (nome de domínio totalmente qualificado) e endereço IP para todos os serviços de borda, incluindo o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V. Se você não selecionar a opção para usar um único FQDN e endereço IP, será necessário especificar um FQDN e um endereço IP separados para cada um desses três serviços de borda como parte do processo de implantação. Para obter detalhes sobre os serviços de borda, consulte [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) na documentação de planejamento.

    > [!NOTE]
    > Se você selecionar essa opção, deve especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta padrão recomendadas: 444 para serviço de borda de acesso, 8057 para serviço de borda de Webconferência e 443 para serviço de borda A/V). Selecionar essa opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode inserir um FQDN usado para todos os três serviços.

- Suporte para Federação. Selecione essa opção se quiser oferecer suporte à comunicação entre usuários internos e usuários em domínios confiáveis fora da sua organização, incluindo qualquer usuário de um provedor de mensagens instantâneas (IM) com suporte. Se você selecionar essa opção, será necessário configurar o suporte para domínios federados específicos e provedores de serviço de conectividade de mensagens instantâneas públicos que você deseja suportar. Para obter detalhes sobre como configurar o suporte para Federação e outros tipos de acesso de usuário externo, consulte [Configuring support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) na documentação de implantação do servidor de borda.

    > [!NOTE]
    > Somente um pool de front-ends ou servidor de borda padrão em sua organização pode ser publicado externamente para Federação. Todos os acessos de usuários federados, incluindo usuários públicos de IM, passam pelo mesmo pool de borda ou servidor de borda único. Por exemplo, se sua implantação inclui um pool de Borda ou único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.

- Habilitar Federação XMPP. Selecione essa opção se quiser oferecer suporte à comunicação entre usuários internos e parceiros XMPP confiáveis.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar Servidores de Borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação Implantação do Servidor de Borda.


