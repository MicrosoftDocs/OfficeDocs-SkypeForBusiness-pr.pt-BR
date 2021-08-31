---
title: Verificar ambiente herdável
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Antes de implantar Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado, antes de implantar um pool piloto Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server XMPP 2019 em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar qual parceiro federado a configuração XMPP herdada está suportando.
ms.openlocfilehash: 208b508eb6b2b5c62da51aa6317cde6e2a95bbb7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727740"
---
# <a name="verify-the-legacy-environment"></a>Verificar o ambiente herdável

Antes de implantar Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado antes de implantar um pool piloto Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server XMPP 2019 em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar qual parceiro federado a configuração XMPP herdada está suportando. Verificar sua implantação herdda envolve o seguinte:
  
- Verificando se os serviços herdamentos foram iniciados
    
- Revisar a topologia e os usuários
    
- Verificando as configurações de servidor de borda e federação
    
- Verificando serviços XMPP e parceiros federados
    
## <a name="verify-that-legacy-services-are-started"></a>Verifique se os serviços herddos foram iniciados

1. No Servidor Front-End herddo, navegue até o applet Ferramentas Administrativas\Serviços.
    
2. Verifique se os serviços a seguir estão sendo executados no servidor Front End:
    
     ![Lista de serviços em execução no Servidor Front-End.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Analisar a topologia herdado no Skype for Business Server Painel de Controle

1. Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.
    
2. Abra o painel Skype for Business Server controle.
    
3. Selecione **Topologia**. Verifique se os vários servidores em sua implantação herdada estão listados.
    
     ![Página de topologia do Painel de Controle.](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Analisar usuários herdado no Skype for Business Server Painel de Controle

1. Abra o painel Skype for Business Server controle.
    
2. Selecione **Usuários** e clique em **Encontrar**.
    
3. Verifique se a **coluna Pool** do Registrador aponta para o pool herdado para cada usuário listado. 
    
     ![Usuários de listagem do Painel de Controle.](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificar configurações de Borda e federação herddas

1. Inicie o Construtor de topologia.
    
2. Selecione **Download da topologia de uma implantação existente**.
    
3. Escolha um nome de arquivo e salve a topologia com o tipo de arquivo .tbxml padrão.
    
4. Expanda o nó de instalação herdados para revelar as várias funções de servidor na implantação.
    
5. Selecione o nó do site e verifique se um valor de atribuição de rota **de federação de site** está definido. 
    
     ![Construtor de Topologias, Rota de Federação de Sites.](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selecione o Edição Standard Server ou Edição Enterprise de front-end. Determinar se um pool de Borda foi configurado para mídia abaixo **de Associações**. 
    
     ![Construtor de Topologias mostrando servidores e pools.](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selecione o pool de borda e identifique se um pool de próximo salto está configurado abaixo da **seleção de Próximo salto**.
    
     ![Construtor de Topologias, Seleção de próximo salto.](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificar configuração de parceiro federado XMPP herdado

1. No servidor XMPP legado, navegue até o applet Ferramentas administrativas\Serviços.
    
2. Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado. 
    
     ![Office Serviço de Gateway XMPP do Communications Server.](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

