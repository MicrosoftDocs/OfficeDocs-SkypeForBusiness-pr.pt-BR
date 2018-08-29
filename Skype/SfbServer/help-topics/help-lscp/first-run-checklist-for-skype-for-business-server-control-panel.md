---
title: Executar primeiro lista de verificação do Painel de Controle do Skype for Business Server.
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Bem-vindo ao Skype para painel de controle do Business Server, a interface de usuário baseada na web para administração e gerenciamento do Skype para Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que eram executados no Console de Gerenciamento Microsoft nas versões anteriores.
ms.openlocfilehash: 56f3b330861b70042d1e30aba76ac33659a6675d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255113"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Executar primeiro lista de verificação do Painel de Controle do Skype for Business Server.

Bem-vindo ao Skype para painel de controle do Business Server, a interface de usuário baseada na web para administração e gerenciamento do Skype para Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que eram executados no Console de Gerenciamento Microsoft nas versões anteriores.

Há um número de tarefas importantes que é altamente recomendável que você executar depois de implantar Skype para Business Server. Algumas destas tarefas são etapas de configuração inicial que você pode já ter executado durante a implantação, enquanto outros são melhorias ou modificações de definições que você configurou durante a implantação ou definições padrão. Outras tarefas descritas neste tópico validam as configurações feitas por você durante o processo de implantação.

> [!NOTE]
> Antes de executar as tarefas na tabela a seguir, certifique-se de que você faça logon usando os direitos de usuário corretos, permissões e role, conforme descrito na seção "Funções e escopo" do tópico [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) .

## <a name="first-run-checklist"></a>Lista de verificação inicial

É altamente recomendável que você revise as tarefas referidas neste tópico e, em seguida, execute os procedimentos adequados para a implantação do Lync Server em sua organização.

|**Tarefa**|**Grupo do Painel de Controle**|**Documentação**|
|:-----|:-----|:-----|
|Verifique se os serviços instalados em sua topologia estão sendo executados como esperado.  <br/> |**Topologia** <br/> |[Exibir detalhes sobre um serviço](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Habilite usuários para Skype para Business Server. Opcionalmente, e, se migrando de uma versão anterior, mover usuários para Skype para Business Server.  <br/> |**Usuários** <br/> |[Gerenciando usuários](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Caso tenha implantado ou queira implantar o Enterprise Voice, configure uma conexão de tronco SIP para habilitar a conectividade à Rede Telefônica Pública Comutada (PSTN).  <br/> |**Roteamento de Voz** <br/> |[Configurando troncos e regras de conversão](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Caso tenha implantado o Enterprise Voice, verifique suas configurações de roteamento.  <br/> |**Roteamento de Voz** <br/> |[Testar roteamento de voz](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Verifique se as políticas e configurações de arquivamento atendem às necessidades de conformidade de sua organização, caso tenha implantado um Servidor de Arquivamento.  <br/> |**Monitoramento e Arquivamento** <br/> |[Gerenciando o arquivamento](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Caso tenha implantado o Servidor de Monitoramento, consulte seus relatórios para visualizar informações sobre uso e diagnóstico.  <br/> |**Página Inicial** <br/> |[Gerenciar a saúde e o monitoramento no Skype for Business Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


