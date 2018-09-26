---
title: Implantar o servidor de borda piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico destaca as definições de configuração, que você deve estar ciente antes de implantar sua Skype para o servidor de borda de 2019 Business Server. Os processos de implantação e configuração de Skype para Business Server 2019 serão bastante similares às Skype para Business Server 2015. Esta seção destaca somente os principais pontos que devem ser considerados como parte da sua implantação do pool piloto. Para obter etapas detalhadas, consulte Implantando o acesso de usuário externo em Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também oferece informações de configuração de acesso de usuário externo.
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029857"
---
# <a name="deploy-pilot-edge-server"></a>Implantar o servidor de borda piloto

Este tópico destaca as definições de configuração, que você deve estar ciente antes de implantar sua Skype para o servidor de borda de 2019 Business Server. Os processos de implantação e configuração de Skype para Business Server 2019 serão bastante similares às Skype para Business Server 2015. Esta seção destaca somente os principais pontos que devem ser considerados como parte da sua implantação do pool piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Enquanto você navega por meio do assistente **Definir Novo Pool de borda** , examine as definições de configuração de chave mostradas nas etapas a seguir. Observe que apenas algumas páginas do assistente **Definir Novo Pool de borda** são mostradas. 
  
### <a name="to-define-an-edge-pool"></a>Para definir um Pool de borda

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Navegue até o Skype para Business Server 2019 nó. Clique com o botão **pools de borda**e clique em **novo pool de borda**.
    
     ![Definir a caixa de diálogo Novo Pool de borda](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Um pool de borda pode ser um **pool de vários computadores** ou **pool de computador único**.
    
     ![Definir a caixa de diálogo de FQDN do Pool de borda](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Na página **Selecionar recursos** , não ative federação ou a federação XMPP. Federação e federação XMPP são ambos atualmente roteadas pelo servidor de borda herdado. Esses recursos serão configurados em uma fase posterior da migração. 

  
5. Continue preenchendo as seguintes páginas do assistente: **FQDNs externos**, **definir o endereço IP interno**e **definir o endereço IP externo**.
    
6. Na página **definir o servidor de próximo salto** , selecione o diretor para o próximo salto do pool de borda herdado. 
    
     ![Definir a caixa de diálogo de próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Na página **associar Front-End ou pools de mediação** , não associe um pool com este pool de borda neste momento. Atualmente, o tráfego de mídia externa é roteado por meio do servidor de borda herdado. Essa configuração será configurada em uma fase posterior da migração. 
    
     ![Caixa de diálogo Associar Pools de Front-End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Clique em **Concluir**e, em seguida, **Publicar** a topologia. 
    
9. Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
É muito importante que você siga as diretrizes nos tópicos na documentação de implantação. Esta seção forneceu meramente algumas diretrizes nas definições de configuração ao instalar essas funções de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Agora, você deve ter um servidor de borda herdado implantado em paralelo com uma Skype para implantação de servidor de borda de 2019 Business Server. Verificar se as implantações estão em execução adequadamente, serviços foram iniciados e você pode administrar cada implantação antes de mover para a próxima fase. 
  

