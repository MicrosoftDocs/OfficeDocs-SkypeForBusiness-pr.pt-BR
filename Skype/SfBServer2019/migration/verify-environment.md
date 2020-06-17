---
title: Verificar o ambiente herdado
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
description: Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes no seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar que parceiro federado a configuração XMPP herdada oferece suporte.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751673"
---
# <a name="verify-the-legacy-environment"></a>Verificar o ambiente herdado

Antes de implantar o Skype for Business Server 2019 em um estado de coexistência, você precisa verificar se os serviços herdados foram configurados e iniciados. É importante identificar os principais serviços e recursos existentes no seu ambiente herdado antes de implantar um pool piloto do Skype for Business Server 2019. Antes de implantar o Microsoft Skype for Business Server 2019 XMPP em um estado de coexistência com uma implantação herdada do XMPP, você precisa verificar se os serviços herdados do XMPP foram configurados e iniciados e identificar o parceiro federado onde a configuração XMPP herdada oferece suporte. Verificar sua implantação herdada envolve o seguinte:
  
- Verificando se os serviços herdados foram iniciados
    
- Examinando a topologia e os usuários
    
- Verificar as configurações de Federação e servidor de borda
    
- Verificando os serviços XMPP e parceiros federados
    
## <a name="verify-that-legacy-services-are-started"></a>Verificar se os serviços herdados foram iniciados

1. No servidor de front-end herdado, navegue até o mini-aplicativo applet administrativo.
    
2. Verifique se os serviços a seguir estão sendo executados no servidor Front End:
    
     ![Lista de serviços em execução no servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Examinar a topologia herdada no painel de controle do Skype for Business Server

1. Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Selecione **Topologia**. Verifique se os vários servidores em sua implantação herdada estão listados.
    
     ![Página de topologia do painel de controle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Revisar usuários herdados no painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.
    
2. Selecione **usuários**e clique em **Localizar**.
    
3. Verifique se a coluna **pool do registrador** aponta para o pool herdado para cada usuário listado. 
    
     ![Painel de controle listando usuários](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Verificar configurações de Federação e borda herdadas

1. Inicie o Construtor de topologia.
    
2. Selecione **Download da topologia de uma implantação existente**.
    
3. Escolha um nome de arquivo e salve a topologia com o tipo de arquivo default. tbxml.
    
4. Expanda o nó instalações herdadas para revelar as várias funções de servidor na implantação.
    
5. Selecione o nó do site e verifique se um valor de **atribuição da rota de Federação do site** está definido. 
    
     ![Construtor de topologias, rota de Federação do site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Selecione o servidor Standard Edition ou o pool de front-ends Enterprise Edition. Determinar se um pool de borda foi configurado para a mídia abaixo de **associações**. 
    
     ![Construtor de topologia mostrando servidores e pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Selecione o pool de borda e identifique se um pool de próximo salto está configurado abaixo da **seleção do próximo salto**.
    
     ![Construtor de topologias, seleção de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Verificar a configuração de parceiro federado XMPP herdado

1. No servidor XMPP legado, navegue até o applet Ferramentas administrativas\Serviços.
    
2. Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado. 
    
     ![Serviço de Gateway XMPP do Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

