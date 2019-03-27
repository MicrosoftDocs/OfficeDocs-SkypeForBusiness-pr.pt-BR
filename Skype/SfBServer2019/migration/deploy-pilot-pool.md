---
title: Implantar pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uma das primeiras etapas necessárias para a migração para Skype para Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testar a coexistência do Skype para Business Server 2019 com sua implantação herdada. Coexistência é um estado temporário que dura até você moveu todos os usuários e os pools para Skype para Business Server 2019.
ms.openlocfilehash: e0ac949b0cc7a52e1da5edd9f150e5f59717c08f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890652"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implantar o Skype para o pool piloto Business Server 2019

Uma das primeiras etapas necessárias para a migração para Skype para Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testar a coexistência do Skype para Business Server 2019 com sua implantação herdada. Coexistência é um estado temporário que dura até você moveu todos os usuários e os pools para Skype para Business Server 2019. 
  
Quando você implanta um pool piloto, você pode usar o assistente Definir Novo Pool Front-End. Você deve implantar os mesmos recursos e cargas de trabalho no seu Skype para pool de piloto Business Server 2019 que você tem no seu pool herdado. Se você implantou o System Center Operations Manager, Monitoring Server ou servidor de arquivamento para fins de arquivamento ou monitoramento seu ambiente herdado, e você deseja continuar o arquivamento ou monitoramento em toda a migração, você precisará também implantar esses recursos no seu ambiente piloto. A versão implantada para arquivar ou monitorar sua herdada ambiente não irá capturar dados em seu Skype para ambiente de negócios Server 2019. 
  
> [!NOTE]
> O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do seu processo de implantação do pool piloto geral. Esta seção destaca somente os principais pontos que devem ser considerados como parte da sua implantação do pool piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implantar um Skype para o pool piloto Business Server 2019

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Expanda a árvore até chegar **Skype para Business Server 2019** > **pools de Front End do Enterprise Edition**.
    
3. **Pools de Front End do Enterprise Edition** do mouse em e selecione **Novo Pool Front-End**.
  
4. Insira o nome de domínio totalmente qualificado (FQDN) do pool. Quando você define seu pool piloto, você pode optar por implantar um pool de Front End do Enterprise Edition ou um servidor Standard Edition. Skype para Business Server 2019 não exige que os recursos de seu pool piloto correspondem o que foi implantado no seu pool herdado.
    
    > [!CAUTION]
    > O pool ou servidor que você define para o pool piloto FQDN deve ser exclusivo. Ele não pode corresponder ao nome do pool herdado implantado atualmente ou qualquer outro servidor atualmente implantado. 
  
5. Na página **Selecionar recursos** , marque as caixas de seleção dos recursos que você deseja desse pool de Front-End. Por exemplo, se você estiver implantando somente mensagens instantâneas (IM) e recursos de presença, você deve selecionar a caixa de seleção de conferência para permitir mensagens Instantâneas com vários participantes, mas você não selecionaria a conferência discada (PSTN), Enterprise Voice, ou verificar Call Admission Control caixas, porque eles representam voice, recursos de conferência de vídeo e de colaboração. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Na página **Selecionar servidor colocado funções** , recomendamos que você escolha colocar o servidor de mediação no Skype para Business Server 2019. Ao mesclar uma topologia herdada com Skype para Business Server 2019, solicitamos que você primeiro colocar o servidor de mediação herdado. Após mesclar as topologias e configurando o Skype para o servidor de mediação de 2019 Business Server, você pode decidir se deseja manter o servidor de mediação colocado ou alterá-la para um servidor autônomo, quando você mover a função de servidor de mediação para Skype para Business Server 2019 posteriormente no processo de implantação. 
   
7. Na página **associar as funções de servidor com este pool de Front-End** , durante a implantação do pool piloto, *não* escolha a opção **Habilitar um pool de borda a ser usado pelo componente de mídia deste pool de Front-End** . Esse é um recurso você habilitará e colocar online em uma fase posterior da migração. Mantenha esta configuração desmarcada por enquanto. 
  
8. Na página **Selecionar um Office Web Apps Server** , clique em **novo**e especifique o FQDN do servidor de aplicativos.
  
9. Na página **definir o repositório de arquivamento do SQL Server** , ao definir o repositório do SQL Server para ambos os Skype para negócios, incluindo servidor de arquivamento e monitoramento, selecione a instância do SQL Server criada anteriormente para Skype para Business Server 2019. 
  
10. Para publicar sua topologia, clique com botão direito no nó do **Skype para Business Server** e, em seguida, clique em **Publicar topologia**.
  
11. Quando o processo de publicação for concluído, clique em **Concluir**.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

