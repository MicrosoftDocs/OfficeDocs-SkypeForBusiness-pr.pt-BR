---
title: Criar Administradores do Painel de Controle do Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para conceder acesso ao Skype for Business Server, faça o seguinte:'
ms.openlocfilehash: 42163cf1df7ae13b918f592b512d3f5fd89169de
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839013"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Criar Administradores do Painel de Controle do Skype for Business Server
 
Para conceder acesso ao Skype for Business Server, faça o seguinte:
  
1. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique com o botão direito do mouse no recipiente **Usuários** e clique em **Propriedades**.
    
3. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
4. Na guia Membros, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
5. Na guia Membros, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
> [!TIP]
> O Skype for Business Server de controle é uma ferramenta de controle de acesso baseada em função. A associação ao grupo CsAdministrator oferece a um usuário que está usando o controle total do Painel de Controle Skype for Business Server para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Os usuários não devem ser habilitados para Skype for Business Server para serem membros dos grupos de gerenciamento. 
  
Outras funções incluem:
  
- **CsArchiving:** Os membros desse grupo podem executar todas as funções de arquivamento, como configurar e gerenciar a função servidor de arquivamento.
    
- **CsHelpDesk:** Membros desse grupo podem exibir a configuração e implantação, incluindo propriedades e políticas de usuário. Os membros também podem executar tarefas de solução de problema específicas.
    
- **CsLocationAdministrator:** Os membros têm o nível mais baixo de direitos de usuário associados ao gerenciamento do 9-1-1 Avançado (E9-1-1). Eles podem criar locais e identificadores de rede do E9-1-1 e associá-los à implantação.
    
- **CsResponseGroupAdministrator:** Os membros podem gerenciar e configurar o serviço do Grupo de Resposta.
    
- **CsServerAdministrator:** Os membros podem gerenciar, monitorar e solucionar problemas de todos os servidores que executam Skype for Business Server.
    
- **CsUserAdministrator:** Os membros podem gerenciar, habilitar e desabilitar os usuários, e atribuir políticas existentes aos usuários.
    
- **CsViewOnlyAdministrator:** Os membros podem exibir a implantação e a configuração das informações do servidor. Essa associação permite que um membro monitore a saúde dos servidores que executam Skype for Business Server.
    
- **CsVoiceAdministrator:** Os membros podem criar, configurar e gerenciar configurações relacionadas à voz Skype for Business Server.
    
Para ajudar a manter a integridade do controle de acesso baseado em função e segurança, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento da implantação Skype for Business Server.
  

