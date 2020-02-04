---
title: Executar primeiro lista de verificação do Painel de Controle do Skype for Business Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Bem-vindo ao painel de controle do Skype for Business Server, a interface do usuário baseada na Web para administração e gerenciamento do Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que eram executados no Console de Gerenciamento Microsoft nas versões anteriores.
ms.openlocfilehash: 9fe3c04746d15e67cc37a8039b3b43db869b1835
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691276"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Executar primeiro lista de verificação do Painel de Controle do Skype for Business Server.

Bem-vindo ao painel de controle do Skype for Business Server, a interface do usuário baseada na Web para administração e gerenciamento do Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que eram executados no Console de Gerenciamento Microsoft nas versões anteriores.

Há várias tarefas importantes que recomendamos que você realize após a implantação do Skype for Business Server. Algumas destas tarefas são etapas de configuração inicial que você pode já ter executado durante a implantação, enquanto outros são melhorias ou modificações de definições que você configurou durante a implantação ou definições padrão. Outras tarefas descritas neste tópico validam as configurações feitas por você durante o processo de implantação.

> [!NOTE]
> Antes de executar as tarefas da tabela abaixo, lembre-se de fazer logon com os privilégios, permissões e funções de usuário corretos, como descrito na seção "Funções e escopo" do tópico [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Lista de verificação inicial

É altamente recomendável que você examine as tarefas citadas neste tópico e execute os procedimentos apropriados para a implantação em sua organização.

|**Tarefa**|**Grupo do Painel de Controle**|**Documentação**|
|:-----|:-----|:-----|
|Verifique se os serviços instalados em sua topologia estão sendo executados como esperado.  <br/> |**Topologia** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Habilite os usuários para o Skype for Business Server. Se quiser e, se estiver migrando de uma versão anterior, mova os usuários para o Skype for Business Server.  <br/> |**Usuários** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Caso tenha implantado ou queira implantar o Enterprise Voice, configure uma conexão de tronco SIP para habilitar a conectividade à Rede Telefônica Pública Comutada (PSTN).  <br/> |**Roteamento de Voz** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Caso tenha implantado o Enterprise Voice, verifique suas configurações de roteamento.  <br/> |**Roteamento de Voz** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Verifique se as políticas e configurações de arquivamento atendem às necessidades de conformidade de sua organização, caso tenha implantado um Servidor de Arquivamento.  <br/> |**Monitoramento e Arquivamento** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Caso tenha implantado o Servidor de Monitoramento, consulte seus relatórios para visualizar informações sobre uso e diagnóstico.  <br/> |**Página Inicial** <br/> |[Gerenciar a integridade e o monitoramento no Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


