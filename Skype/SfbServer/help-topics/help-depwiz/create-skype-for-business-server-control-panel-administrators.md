---
title: Criar Administradores de Painel de Controle do Skype for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Para conceder acesso para o Skype para Business Server 2015, faça o seguinte:'
ms.openlocfilehash: 5d01066da5be34ba53f4eca37d35a3913d07142a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201336"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Criar Administradores de Painel de Controle do Skype for Business Server
 
Para conceder acesso para o Skype para Business Server 2015, faça o seguinte:
  
1. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique com o botão direito do mouse no contêiner **Usuários** e clique em **Propriedades**.
    
3. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
4. Na guia Membros, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
5. Na guia Membros, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
> [!TIP]
> O Skype para painel de controle do Business Server é uma ferramenta de controle de acesso baseado em função. A associação ao grupo CsAdministrator oferece um usuário que você está usando o Skype para controle total do painel de controle do servidor de negócios para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Os usuários não precisam estar habilitado para Skype para Business Server para se tornar membros dos grupos de gerenciamento. 
  
Outras funções incluem:
  
- **CsArchiving:** Membros desse grupo podem executar todas as funções de arquivamento, como configurar e gerenciar a função de servidor de arquivamento.
    
- **CsHelpDesk:** Membros desse grupo podem exibir a configuração e implantação, incluindo propriedades e políticas de usuário. Os membros também podem executar tarefas específicas de solução de problemas.
    
- **CsLocationAdministrator:** Os membros têm o nível mais baixo de direitos de usuário associados ao gerenciamento do 9-1-1 Avançado (E9-1-1). Eles podem criar locais e identificadores de rede do E9-1-1 e associá-los à implantação.
    
- **CsResponseGroupAdministrator:** Os membros podem gerenciar e configurar o serviço do Grupo de Resposta.
    
- **CsServerAdministrator:** Membros podem gerenciar, monitorar e solucionar problemas de todos os servidores que executam o Skype para Business Server.
    
- **CsUserAdministrator:** Os membros podem gerenciar, habilitar e desabilitar os usuários, e atribuir políticas existentes aos usuários.
    
- **CsViewOnlyAdministrator:** Os membros podem exibir a implantação e a configuração das informações do servidor. Essa associação permite que o membro para monitorar a integridade dos servidores que executam o Skype para Business Server 2015.
    
- **CsVoiceAdministrator:** Os membros podem criar, configurar e gerenciar configurações relacionadas à voz no Skype para Business Server.
    
Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento do Skype para implantação de servidor de negócios.
  

