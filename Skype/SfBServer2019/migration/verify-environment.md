---
title: Verificar o ambiente herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos que existem em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identifica qual parceiro federado a configuração de XMPP herdada é support.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280657"
---
# <a name="verify-the-legacy-environment"></a>Verificar o ambiente herdado

Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes em seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar qual parceiro federado a XMPP herdada a configuração tem suporte. Verificar sua implantação herdada envolve o seguinte:
  
- Verificar se os serviços herdados foram iniciados
    
- Revisando a topologia e os usuários
    
- Verificando as configurações do servidor de Federação e de borda
    
- Verificando os serviços do XMPP e parceiros federados
    
## <a name="verify-that-legacy-services-are-started"></a>Verificar se os serviços herdados foram iniciados

1. No servidor front-end herdado, navegue até o applet de Tools\Services administrativo.
    
2. Verifique se os seguintes serviços estão em execução no servidor front-end:
    
     ![Lista de serviços em execução no front-end Server](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Examine a topologia herdada no painel de controle do Skype for Business Server

1. Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Selecione **topologia**. Verifique se os vários servidores na sua implantação herdada estão listados.
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Examine os usuários herdados no painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.
    
2. Selecione **usuários**e, em seguida, clique em **Localizar**.
    
3. Verifique se a coluna **pool** de registradores aponta para o pool herdado para cada usuário listado. 
    
     ![Listar usuários do painel de controle](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificar as configurações de borda e de Federação herdadas

1. Iniciar o construtor de topologias.
    
2. Selecione **baixar a topologia na implantação existente**.
    
3. Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.
    
4. Expanda o nó instalações herdadas para revelar as várias funções de servidor na implantação.
    
5. Selecione o nó do site e verifique se um valor de **atribuição da rota de Federação do site** está definido. 
    
     ![Construtor de topologias, roteiro de Federação do site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selecione o servidor Standard Edition ou o pool Front-end Enterprise Edition. Determine se um pool de bordas foi configurado para mídia abaixo de **associações**. 
    
     ![Construtor de topologias mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selecione o pool de bordas e identifique se um próximo pool de saltos está configurado abaixo da **próxima seleção de salto**.
    
     ![Construtor de topologias, seleção do próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificar a configuração de parceiro federado do XMPP herdado

1. No servidor herdado XMPP, navegue até o applet administrador Tools\Services.
    
2. Verifique se o serviço do Gateway XMPP do Office Communications Server foi iniciado. 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

