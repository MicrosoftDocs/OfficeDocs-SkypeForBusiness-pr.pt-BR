---
title: Implantar pool piloto
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
description: Uma das primeiras etapas necessárias para migrar para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até você ter movido todos os usuários e pools para o Skype for Business Server 2019.
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113287"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implantar o pool piloto do Skype for Business Server 2019

Uma das primeiras etapas necessárias para migrar para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até você ter movido todos os usuários e pools para o Skype for Business Server 2019. 
  
Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Skype for Business Server 2019 que você tem no pool herdado. Se você implantou o Servidor de Arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento do seu ambiente herdado e deseja continuar o arquivamento ou o monitoramento durante toda a migração, você também precisará implantar esses recursos em seu ambiente piloto. A versão implantada para arquivar ou monitorar seu ambiente herdado não capturará dados em seu ambiente do Skype for Business Server 2019. 
  
> [!NOTE]
> O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implantar um pool piloto do Skype for Business Server 2019

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Expanda a árvore até chegar aos pools de Front-End do **Skype for Business Server 2019** Enterprise  >  **Edition.**
    
3. Clique com o botão direito do mouse em **Pools front-end** do Enterprise Edition e selecione **Novo Pool de Front-End**.
  
4. Insira o FQDN (nome de domínio totalmente qualificado) do pool. Ao definir seu pool piloto, você pode optar por implantar um pool de Front-End do Enterprise Edition ou um servidor Standard Edition. O Skype for Business Server 2019 não exige que os recursos do pool piloto corresponderem ao que foi implantado no pool herdado.
    
    > [!CAUTION]
    > O FQDN do pool ou do servidor definido para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool herdado implantado no momento ou qualquer outro servidor implantado no momento. 
  
5. Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se você estiver implantando apenas recursos de IM (mensagens instantâneas) e presença, você selecionaria a caixa de seleção Conferência para permitir mensagens instantâneas com várias partes, mas não selecionaria as caixas de seleção Conferência discadas (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, pois elas representam recursos de voz, vídeo e conferência colaborativa. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Na página **Selecionar funções de** servidor alocadas, recomendamos que você escolha a colocar o Servidor de Mediação no Skype for Business Server 2019. Ao mesclar uma topologia herdada com o Skype for Business Server 2019, exigimos que você primeiro cole o Servidor de Mediação herdada. Depois de mesclar as topologias e configurar o Servidor de Mediação do Skype for Business Server 2019, você pode decidir se deve manter o Servidor de Mediação alocado ou alterá-lo para um servidor autônomo ao mover a função servidor de mediação para o Skype for Business Server 2019 posteriormente no processo de implantação. 
   
7. Na página Associar funções de servidor a esse pool de **Front-End,** durante a implantação do pool *piloto,* não escolha a opção Habilitar um pool de Borda a ser usado pelo componente de mídia desta opção **de pool de Front-End.** Esse é um recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto. 
  
8. Na página **Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.
  
9. Na página Definir o SQL Server **de** arquivamento, ao definir o armazenamento SQL Server para Arquivamento e Monitoramento do Skype for Business Server, selecione SQL Server instância criada anteriormente para o Skype for Business Server 2019. 
  
10. Para publicar sua topologia, clique com o botão direito do mouse no nó **Skype for Business Server** e clique em Publicar **Topologia**.
  
11. Quando o processo de publicação for concluído, clique em **Finalizar**.

12. Antes de mover para a próxima seção chamada "Verificar a coexistência do pool piloto com o pool herdado", você precisa instalar o novo pool piloto de Front End do Skype for Business Server que acabamos de definir na topologia publicada, siga os procedimentos descritos aqui Instalar o Skype for Business Server em servidores na [topologia](../../SfbServer/deploy/install/install-skype-for-business-server.md)

13. Depois que a etapa anterior for concluída, vá para a próxima seção para Verificar a coexistência do pool piloto com o pool herdado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
