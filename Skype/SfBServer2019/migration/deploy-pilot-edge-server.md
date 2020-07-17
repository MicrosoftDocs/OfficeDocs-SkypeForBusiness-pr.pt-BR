---
title: Implantar um Servidor de Borda piloto
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
description: Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. Para obter etapas detalhadas, consulte Deploying external User Access in Skype for Business Server 2019 na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752863"
---
# <a name="deploy-pilot-edge-server"></a>Implantar um Servidor de Borda piloto

Este tópico realça as definições de configuração que você deve estar ciente antes de implantar seu servidor de borda do Skype for Business Server 2019. Os processos de implantação e configuração do Skype for Business Server 2019 são muito semelhantes ao Skype for Business Server 2015. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Conforme você navega pelo assistente **Definir Novo Pool de Borda**, reveja as principais definições de configuração exibidas nas etapas a seguir. Observe que somente algumas páginas do assistente **Definir Novo Pool de Borda** são mostradas. 
  
### <a name="to-define-an-edge-pool"></a>Para definir um pool de borda

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Navegue até o nó do Skype for Business Server 2019. Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.
    
     ![Caixa de diálogo Definir novo pool de borda](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.
    
     ![Caixa de diálogo definir o FQDN do pool de borda](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP. A Federação e a Federação XMPP são roteadas atualmente através do servidor de borda herdado. Estes recursos são configurados em uma fase posterior da migração. 

  
5. Continue preenchendo as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.
    
6. Na página **definir o servidor de próximo salto** , selecione o diretor para o próximo salto do pool de borda herdado. 
    
     ![Caixa de diálogo Definir próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Na página **associar pools de front-ends ou de mediação** , não associe um pool a este pool de borda neste momento. No momento, o tráfego de mídia externo é roteado através do servidor de borda herdado. Esta definição será configurada em uma fase posterior de migração. 
    
     ![Caixa de diálogo associar pools de front-ends](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Clique em **concluir**e **publique** a topologia. 
    
9. Siga as etapas na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
É muito importante que você siga as diretrizes nos tópicos da documentação de implantação. Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Agora você deve ter um servidor de borda herdado implantado em paralelo com uma implantação do servidor de borda do Skype for Business Server 2019. Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se você pode administrar cada implantação antes de seguir para a próxima fase. 
  

