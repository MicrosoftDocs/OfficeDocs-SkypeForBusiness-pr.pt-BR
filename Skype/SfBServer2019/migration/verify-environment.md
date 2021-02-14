---
title: Verificar o ambiente herddo
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado, antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar a qual parceiro federado a configuração XMPP herdada é suportada.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751673"
---
# <a name="verify-the-legacy-environment"></a>Verificar o ambiente herddo

Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o XMPP do Microsoft Skype for Business Server 2019 em um estado de coexistência com uma implantação XMPP herdada, você precisa verificar se os serviços XMPP herdados foram configurados e iniciados e identificar a qual parceiro federado a configuração XMPP herdada é suportada. A verificação da implantação herdda envolve o seguinte:
  
- Verificando se os serviços herddos foram iniciados
    
- Revendo a topologia e os usuários
    
- Verificando as configurações do servidor de borda e federação
    
- Verificando serviços XMPP e parceiros federados
    
## <a name="verify-that-legacy-services-are-started"></a>Verificar se os serviços herddos foram iniciados

1. No Servidor front-end herddo, navegue até o applet Ferramentas Administrativas\Serviços.
    
2. Verifique se os serviços a seguir estão sendo executados no servidor Front End:
    
     ![Lista de serviços em execução no Servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Revisar a topologia herdada no Painel de Controle do Skype for Business Server

1. Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.
    
2. Abra o Painel de Controle do Skype for Business Server.
    
3. Selecione **Topologia**. Verifique se os vários servidores em sua implantação herdada estão listados.
    
     ![Página de topologia do Painel de Controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revisar usuários herdado no Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.
    
2. Selecione **Usuários** e clique em **Encontrar.**
    
3. Verifique se a coluna **Pool do Registrador** aponta para o pool herdado de cada usuário listado. 
    
     ![Painel de Controle listando usuários](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificar configurações de federação e borda herddas

1. Inicie o Construtor de topologia.
    
2. Selecione **Download da topologia de uma implantação existente**.
    
3. Escolha um nome de arquivo e salve a topologia com o tipo de arquivo .tbxml padrão.
    
4. Expanda o nó de instalação herdados para revelar as várias funções de servidor na implantação.
    
5. Selecione o nó do site e verifique se um valor de atribuição **de rota de federação** do site está definido. 
    
     ![Construtor de Topologias, Rota de Federação do Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selecione o pool de front-end do Servidor Standard Edition ou Enterprise Edition. Determine se um pool de Borda foi configurado para mídia abaixo **de Associações**. 
    
     ![Construtor de Topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selecione o pool de Borda e identifique se um pool de próximo salto está configurado abaixo da **seleção de próximo salto.**
    
     ![Construtor de Topologias, Seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificar configuração de parceiro federado XMPP herdado

1. No servidor XMPP legado, navegue até o applet Ferramentas administrativas\Serviços.
    
2. Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado. 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

