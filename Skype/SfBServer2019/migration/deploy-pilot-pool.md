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
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752853"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implantar o pool piloto do Skype for Business Server 2019

Uma das primeiras etapas necessárias para migrar para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até você ter movido todos os usuários e pools para o Skype for Business Server 2019. 
  
Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends. Você deve implantar os mesmos recursos e cargas de trabalho em seu pool piloto do Skype for Business Server 2019 que você tem em seu pool herdado. Se você implantou o Servidor de Arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente herdado e deseja continuar o arquivamento ou monitoramento durante toda a migração, também precisará implantar esses recursos em seu ambiente piloto. A versão implantada para arquivar ou monitorar seu ambiente herdado não capturará dados em seu ambiente do Skype for Business Server 2019. 
  
> [!NOTE]
> O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implantar um pool piloto do Skype for Business Server 2019

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Expanda a árvore até chegar aos pools de front-end do **Skype for Business Server 2019** Enterprise  >  **Edition.**
    
3. Clique com o botão **direito do mouse nos pools de front-end do Enterprise Edition** e selecione Novo Pool de **Front-End.**
  
4. Insira o FQDN (nome de domínio totalmente qualificado) do pool. Ao definir seu pool piloto, você pode optar por implantar um pool de Front-End Enterprise Edition ou um servidor Standard Edition. O Skype for Business Server 2019 não exige que os recursos do seu pool piloto corresponderem ao que foi implantado em seu pool herdado.
    
    > [!CAUTION]
    > O FQDN do pool ou servidor definido para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool herdado implantado no momento ou de qualquer outro servidor atualmente implantado. 
  
5. Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se você estiver implantando apenas mensagens instantâneas (IM) e recursos de presença, marque a caixa de seleção Conferência para permitir mensagens instantâneas com vários grupos, mas não marque as caixas de seleção Conferência Discado (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, pois elas representam recursos de voz, vídeo e conferência colaborativa. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Na página **Selecionar funções** de servidor alocadas, recomendamos que você escolha o servidor de mediação no Skype for Business Server 2019. Ao mesclar uma topologia herdada com o Skype for Business Server 2019, exigimos que você primeiro collocate o Servidor de Mediação herdada. Depois de mesclar as topologias e configurar o Servidor de Mediação do Skype for Business Server 2019, você poderá decidir se manterá o Servidor de Mediação alocado ou alterá-lo para um servidor autônomo ao mover a função de Servidor de Mediação para o Skype for Business Server 2019 posteriormente no processo de implantação. 
   
7. Na página Associar funções de servidor a este pool de **Front-End,** durante a implantação do pool *piloto,* não escolha Habilitar um pool de Borda a ser usado pelo componente de mídia desta opção de pool de **Front-End.** Esse é um recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto. 
  
8. Na página **Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.
  
9. Na página Definir o armazenamento do **SQL Server** de Arquivamento, ao definir o armazenamento do SQL Server para Arquivamento e Monitoramento do Skype for Business Server, selecione a instância do SQL Server criada anteriormente para o Skype for Business Server 2019. 
  
10. Para publicar sua topologia, clique com o botão direito do mouse no **nó do Skype for Business Server** e clique em Publicar **Topologia.**
  
11. Quando o processo de publicação for concluído, clique em **Finalizar**.

12. Antes de passar para a próxima seção chamada "Verificar coexistência do pool piloto com pool herdado", você precisa instalar o novo pool piloto de Front End do Skype for Business Server que acabamos de definir na topologia publicada, siga os procedimentos descritos aqui Instalar o Skype for Business Server em servidores na [topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Quando a etapa anterior for concluída, vá para a próxima seção para Verificar a coexistência do pool piloto com o pool herdado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

