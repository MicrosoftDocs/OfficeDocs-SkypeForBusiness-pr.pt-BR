---
title: Lista de Verificação da Primeira Execução para o Painel de controle do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Bem-vindo ao Painel de Controle do Skype for Business Server, a interface do usuário baseada na Web para administração e gerenciamento do Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que foram executadas usando o Console de Gerenciamento Microsoft em versões anteriores.
ms.openlocfilehash: 74c1d4ae7b9ed65932acf5b8491a2cd00c67831c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804891"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de Verificação da Primeira Execução para o Painel de controle do Skype for Business Server

Bem-vindo ao Painel de Controle do Skype for Business Server, a interface do usuário baseada na Web para administração e gerenciamento do Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que foram executadas usando o Console de Gerenciamento Microsoft em versões anteriores.

Há várias tarefas importantes que recomendamos que você execute depois de ter implantado o Skype for Business Server. Algumas destas tarefas são etapas de configuração inicial que você pode já ter executado durante a implantação, enquanto outros são melhorias ou modificações de definições que você configurou durante a implantação ou definições padrão. Outras tarefas descritas neste tópico validam as configurações feitas por você durante o processo de implantação..

> [!NOTE]
> Antes de executar as tarefas na tabela a seguir, faça logoff usando os direitos, permissões e funções [](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) de usuário corretos, conforme descrito na seção "Funções e Escopo" do tópico Controle de Acesso Baseado em Função.

## <a name="first-run-checklist"></a>Lista de checagem de Primeira Execução

Recomendamos que você revise as tarefas mencionadas neste tópico e execute os procedimentos apropriados para a implantação do Lync Server em sua organização.

|**Tarefa**|**Grupo do Painel de Controle**|**Documentação**|
|:-----|:-----|:-----|
|Verifique se os serviços instalados em sua topologia estão sendo executados como esperado.  <br/> |**Topologia** <br/> |[Exibir detalhes sobre um serviço](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Habilitar usuários para o Skype for Business Server. Opcionalmente e, se estiver migrando de uma versão anterior, mova os usuários para o Skype for Business Server.  <br/> |**Usuários** <br/> |[Gerenciando usuários](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Caso tenha implantado ou queira implantar o Enterprise Voice, configure uma conexão de tronco SIP para habilitar a conectividade às PSTN (redes telefônicas públicas comutadas).  <br/> |**Roteamento de Voz** <br/> |[Configurando troncos e regras de conversão](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Verifique as configurações de roteamento de Enterprise Voice caso o tenha implantado.  <br/> |**Roteamento de Voz** <br/> |[Testar roteamento de voz](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Verifique se as políticas e configurações de arquivamento atendem às necessidades de conformidade de sua organização, caso tenha implantado um Servidor de Arquivamento.  <br/> |**Monitoramento e Arquivamento** <br/> |[Gerenciando arquivamento](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Veja relatórios do Servidor de Monitoramento para visualizar informações de uso e diagnósticos, caso o tenha implantado.  <br/> |**Página Inicial** <br/> |[Gerenciar a saúde e monitoramento no Skype for Business Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


