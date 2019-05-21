---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. Para obter etapas detalhadas, consulte Implantando o acesso de usuários externos no Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280914"
---
# <a name="deploy-pilot-edge-server"></a>Implantar um Servidor de Borda piloto

Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir. Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas. 
  
### <a name="to-define-an-edge-pool"></a>Para definir um pool de bordas

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Navegue até o nó Skype for Business Server 2019. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
     ![Definir a caixa de diálogo novo pool de bordas](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.
    
     ![Definir a caixa de diálogo FQDN do pool de bordas](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP. A Federação e a Federação do XMPP são roteadas atualmente por meio do servidor de borda herdado. Esses recursos serão configurados em uma fase posterior da migração. 

  
5. Continue a concluir as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.
    
6. Na página **definir o servidor de salto seguinte** , selecione o diretor para o próximo nó do pool de bordas herdado. 
    
     ![Definir a caixa de diálogo salto seguinte](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Na página **associar front-end ou pool** de mediação, não associe um pool a este pool de bordas no momento. No momento, o tráfego de mídia externo é roteado pelo servidor de borda herdado. Essa configuração será configurada em uma fase posterior da migração. 
    
     ![Caixa de diálogo associar grupos de front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Clique em **concluir**e **publique** a topologia. 
    
9. Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
É muito importante que você siga as diretrizes nos tópicos da documentação de implantação. Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Agora você deve ter um servidor de borda herdado implantado em paralelo com uma implantação do servidor de borda do Skype for Business Server 2019. Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase. 
  

