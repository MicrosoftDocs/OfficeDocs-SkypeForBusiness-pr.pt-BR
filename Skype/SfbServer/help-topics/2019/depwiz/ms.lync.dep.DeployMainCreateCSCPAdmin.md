---
title: Criar Administradores de Painel de Controle do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para conceder acesso ao servidor do Skype for Business, faça o seguinte:'
ms.openlocfilehash: 6a605f77c5f2b04804506592ab61c7988d68acfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298166"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Criar Administradores de Painel de Controle do Skype for Business Server
 
Para conceder acesso ao servidor do Skype for Business, faça o seguinte:
  
1. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique com o botão direito do mouse no contêiner **Usuários** e clique em **Propriedades**.
    
3. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
4. Na guia Membros, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
5. Na guia Membros, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
> [!TIP]
> O painel de controle do Skype for Business Server é uma ferramenta de controle de acesso baseada em função. A associação no grupo CsAdministrator permite que um usuário que está usando o painel de controle do Skype for Business Server controle total para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Os usuários não precisam estar habilitados para o Skype for Business Server, a fim de se tornarem membros dos grupos de gerenciamento. 
  
Outras funções incluem:
  
- **CsArchiving:** Os membros desse grupo podem executar todas as funções de arquivamento, como configurar e gerenciar a função de servidor de arquivamento.
    
- **CsHelpDesk:** Membros desse grupo podem exibir a configuração e implantação, incluindo propriedades e políticas de usuário. Os membros também podem executar tarefas específicas de solução de problemas.
    
- **CsLocationAdministrator:** Os membros têm o nível mais baixo de direitos de usuário associados ao gerenciamento do 9-1-1 Avançado (E9-1-1). Eles podem criar locais e identificadores de rede do E9-1-1 e associá-los à implantação.
    
- **CsResponseGroupAdministrator:** Os membros podem gerenciar e configurar o serviço do Grupo de Resposta.
    
- **CsServerAdministrator:** Os membros podem gerenciar, monitorar e solucionar problemas com todos os servidores que executam o Skype for Business Server.
    
- **CsUserAdministrator:** Os membros podem gerenciar, habilitar e desabilitar os usuários, e atribuir políticas existentes aos usuários.
    
- **CsViewOnlyAdministrator:** Os membros podem visualizar a implantação e a configuração das informações do servidor. Esta associação permite que um membro monitore a integridade dos servidores que executam o Skype for Business Server.
    
- **CsVoiceAdministrator:** Os membros podem criar, configurar e gerenciar as configurações relacionadas à voz no Skype for Business Server.
    
Para ajudar a reter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento da implantação do Skype for Business Server.
  

