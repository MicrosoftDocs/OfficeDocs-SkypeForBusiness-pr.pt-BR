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
ms.localizationpriority: medium
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Bem-vindo ao Skype for Business Server de controle, a interface de usuário baseada na Web para administração e gerenciamento de Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que foram executadas usando o Console de Gerenciamento da Microsoft em versões anteriores.
ms.openlocfilehash: 39fe263d41be18068935811efaec923473e59c95
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580785"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Lista de Verificação da Primeira Execução para o Painel de controle do Skype for Business Server

Bem-vindo ao Skype for Business Server de controle, a interface de usuário baseada na Web para administração e gerenciamento de Skype for Business Server. Você pode usar o painel de controle para executar os tipos de tarefas administrativas que foram executadas usando o Console de Gerenciamento da Microsoft em versões anteriores.

Há várias tarefas importantes que recomendamos que você execute após a implantação Skype for Business Server. Algumas destas tarefas são etapas de configuração inicial que você pode já ter executado durante a implantação, enquanto outros são melhorias ou modificações de definições que você configurou durante a implantação ou definições padrão. Outras tarefas descritas neste tópico validam as configurações feitas por você durante o processo de implantação..

> [!NOTE]
> Antes de executar as tarefas na tabela a seguir, [certifique-se](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) de fazer logoff usando os direitos, permissões e função corretos do usuário, conforme descrito na seção "Funções e Escopo" do tópico Controle de Acesso Baseado em Função.

## <a name="first-run-checklist"></a>Lista de checagem de Primeira Execução

Recomendamos que você revise as tarefas mencionadas neste tópico e execute os procedimentos apropriados para a implantação do Lync Server em sua organização.

|**Task**|**Grupo painel de controle**|**Documentação**|
|:-----|:-----|:-----|
|Verifique se os serviços instalados em sua topologia estão sendo executados como esperado.  <br/> |**Topologia** <br/> |[Exibir detalhes sobre um serviço](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|Habilitar usuários para Skype for Business Server. Opcionalmente e, se migrar de uma versão anterior, mova os usuários para Skype for Business Server.  <br/> |**Usuários** <br/> |[Gerenciando usuários](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|Caso tenha implantado ou queira implantar o Enterprise Voice, configure uma conexão de tronco SIP para habilitar a conectividade às PSTN (redes telefônicas públicas comutadas).  <br/> |**Roteamento de Voz** <br/> |[Configurando troncos e regras de conversão](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|Verifique as configurações de roteamento de Enterprise Voice caso o tenha implantado.  <br/> |**Roteamento de Voz** <br/> |[Testar roteamento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|Verifique se as políticas e configurações de arquivamento atendem às necessidades de conformidade de sua organização, caso tenha implantado um Servidor de Arquivamento.  <br/> |**Monitoramento e Arquivamento** <br/> |[Managing Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|Veja relatórios do Servidor de Monitoramento para visualizar informações de uso e diagnósticos, caso o tenha implantado.  <br/> |**Página Inicial** <br/> |[Gerenciar a saúde e o monitoramento no Skype for Business Server 2015](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |