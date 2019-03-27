---
title: Verifique se o ambiente de legado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o Skype para negócios 2019 de servidor em um estado de coexistência, você precisará verificar se os serviços de legado foi configurados e iniciados. É importante identificar os principais serviços e recursos que existem no seu ambiente herdado, antes de implantar um Skype para o pool piloto Business Server 2019. Antes de implantar o Microsoft Skype para Business Server 2019 XMPP em um estado de coexistência com uma implantação de XMPP herdado, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identifique qual parceiro federado é a configuração de XMPP herdado dando suporte.
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887343"
---
# <a name="verify-the-legacy-environment"></a>Verificar o ambiente de legado

Antes de implantar o Skype para negócios 2019 de servidor em um estado de coexistência, você precisará verificar se os serviços de legado foi configurados e iniciados. É importante identificar os principais serviços e recursos que existem no seu ambiente herdado antes de implantar um Skype para o pool piloto Business Server 2019. Antes de implantar o Microsoft Skype para Business Server 2019 XMPP em um estado de coexistência com uma implantação de XMPP herdado, você precisa verificar se os serviços XMPP herdados foram configurados e foram iniciados e identificar quais federados parceiro XMPP herdado suporte a configuração. Verificando a implantação herdada envolve o seguinte:
  
- Verificando se os serviços de legado foram iniciados
    
- Analisando a topologia e os usuários
    
- Verificando a federação e as configurações do servidor de borda
    
- Verificando serviços XMPP e parceiros federados
    
## <a name="verify-that-legacy-services-are-started"></a>Verificar se os serviços legados foram iniciados

1. No herdado servidor Front-End, navegue até o applet ferramentas administrativas \ Serviços.
    
2. Verifique se os seguintes serviços estão funcionando no servidor Front-End:
    
     ![Lista de serviços em execução no servidor Front-End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revise a topologia herdada no Skype para painel de controle do servidor de negócios

1. Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.
    
2. Abra o Skype para painel de controle do servidor de negócios.
    
3. Selecione a **topologia**. Verificar se os vários servidores em sua implantação herdada estão listados.
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revise os usuários herdados do Skype para painel de controle do servidor de negócios

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Selecione **usuários**e, em seguida, clique em **Localizar**.
    
3. Verifique se a coluna **Pool do registrador** aponta para o pool herdado para cada usuário listado. 
    
     ![Listar usuários do painel de controle](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificar as configurações de borda e federação de legado

1. Inicie o construtor de topologias.
    
2. Selecione **Baixar topologia da implantação existente**.
    
3. Escolha um nome de arquivo e salve a topologia com o tipo de arquivo. tbxml padrão.
    
4. Expanda o nó de instalações herdadas para revelar várias funções de servidor na implantação.
    
5. Selecione o nó do site e verificar se um valor de **atribuição de rota de federação local** está definido. 
    
     ![Construtor de topologias, rota de Federação do Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selecione o pool de front-end do servidor Standard Edition ou Enterprise Edition. Determine se um pool de borda foi configurado para a mídia abaixo **associações**. 
    
     ![Construtor de topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selecione o pool de borda e identifique se um pool de próximo salto está configurado abaixo de **seleção do próximo salto**.
    
     ![Construtor de topologias, seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verifique se o parceiro federado de XMPP herdado configuração

1. No servidor XMPP legado, navegue até o applet ferramentas administrativas \ Serviços.
    
2. Verifique se o serviço de Gateway XMPP do Office Communications Server é iniciado. 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

