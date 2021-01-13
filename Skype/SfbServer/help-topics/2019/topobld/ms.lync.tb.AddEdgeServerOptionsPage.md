---
title: Adicionar Opções de Servidor de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 'Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda dá suporte a usuários remotos em sua organização que se insere de fora do firewall usando uma rede virtual privada (VPN). Você também tem as seguintes opções de recurso de pool de Borda:'
ms.openlocfilehash: 943a2a7b96fa8bcfd00e3c21631f763ad056b31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800931"
---
# <a name="add-edge-server-options"></a>Adicionar Opções de Servidor de Borda

Selecione cada recurso que você deseja habilitar para o pool de Borda. Por padrão, o pool de Borda dá suporte a usuários remotos em sua organização que se insere de fora do firewall usando uma rede virtual privada (VPN). Você também tem as seguintes opções de recurso de pool de Borda:

- Uso de um único nome de domínio totalmente qualificado (FQDN) e endereço IP para todos os serviços de borda, incluindo o serviço de Borda de Acesso, o serviço de Borda de Webconferência e o serviço de Borda A/V. Se você não selecionar a opção de usar um único FQDN e endereço IP, precisará especificar um FQDN e um endereço IP separados para cada um desses três serviços de Borda como parte do processo de implantação. Para obter detalhes sobre os serviços de Borda, consulte [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) na documentação planejamento.

    > [!NOTE]
    > Se você selecionar essa opção, deverá especificar um número de porta diferente para cada um dos serviços de Borda (configurações de porta padrão recomendadas: 444 para serviço de Borda de Acesso, 8057 para serviço de Borda de Webconferência e 443 para serviço de Borda A/V). Selecionar essa opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode inserir um FQDN usado para todos os três serviços.

- Suporte para federação. Selecione essa opção se quiser dar suporte à comunicação entre usuários internos e usuários em domínios confiáveis fora da sua organização, incluindo qualquer usuário de um provedor de mensagens instantâneas (IM) público com suporte. Se você selecionar essa opção, precisará configurar o suporte para os domínios federados específicos e os provedores de serviços públicos de conectividade de IM aos quais deseja dar suporte. Para obter detalhes sobre como configurar o suporte para federação e outros tipos de acesso de usuário externo, consulte [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) na documentação de Implantação do Servidor de Borda.

    > [!NOTE]
    > Somente um pool de Front-End ou Servidor de Borda Padrão em sua organização pode ser publicado externamente para federação. Todo o acesso de usuários federados, incluindo usuários públicos de IM, passa pelo mesmo pool de Borda ou servidor de borda único. Por exemplo, se sua implantação inclui um pool de Borda ou único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.

- Habilitar federação XMPP. Selecione essa opção se quiser dar suporte à comunicação entre usuários internos e parceiros XMPP confiáveis.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar Servidores de Borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação Implantação do Servidor de Borda.


