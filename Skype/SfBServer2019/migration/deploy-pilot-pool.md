---
title: Implantar pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uma das primeiras etapas necessárias para a migração para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Skype for Business Server 2019.
ms.openlocfilehash: 3642d603b5923a554b8eca41a948125ef25526ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280861"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implantar o pool piloto do Skype for Business Server 2019

Uma das primeiras etapas necessárias para a migração para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Skype for Business Server 2019. 
  
Ao implantar um pool piloto, use o assistente para definir novo pool de front-end. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Skype for Business Server 2019 que você tem em seu pool herdado. Se você implantou o arquivamento do servidor, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente herdado e deseja continuar a arquivar ou monitorar durante a migração, também é necessário implantar esses recursos em seu ambiente piloto. A versão que você implantou para arquivar ou monitorar seu ambiente herdado não capturará dados no ambiente do Skype for Business Server 2019. 
  
> [!NOTE]
> O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do processo de implantação do pool piloto geral. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implantar um pool piloto do Skype for Business Server 2019

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Expanda a árvore até acessar os pools de**front-end**do **Skype for Business Server 2019** > Enterprise Edition.
    
3. Clique com o botão direito em pools do **front end do Enterprise Edition** e selecione **novo pool de front-end**.
  
4. Digite o nome de domínio totalmente qualificado (FQDN) do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-end do Enterprise Edition ou um servidor Standard Edition. O Skype for Business Server 2019 não requer que seus recursos de pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    > [!CAUTION]
    > O pool ou o FQDN do servidor que você define para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool herdado atualmente implantado ou a qualquer outro servidor atualmente implantado. 
  
5. Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends. Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas você não selecionará a conferência de discagem (PSTN), o Enterprise Voice ou a verificação de controle de admissão de chamadas as caixas, como representam recursos de voz, vídeo e conferência colaborativa. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Na página **selecionar funções de servidor posicionadas** , recomendamos que você opte por posicionar o servidor de mediação no Skype for Business Server 2019. Ao mesclar uma topologia herdada com o Skype for Business Server 2019, precisamos que você primeiro a posicionar o servidor de mediação herdada. Depois de mesclar as topologias e configurar o servidor de mediação do Skype for Business Server 2019, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo em um servidor autônomo ao mover a função do servidor de mediação para o Skype for Business Server 2019 mais tarde no processo de implantação. 
   
7. Na página **associar funções de servidor a este pool de front-end** , durante a implantação do pool piloto, *não* escolha **habilitar um pool de bordas para ser usado pelo componente de mídia dessa opção do pool de front-end** . Este é um recurso que você habilitará e colocará online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto. 
  
8. Na página **selecionar um servidor dos Office Web Apps** , clique em **novo**e especifique o FQDN do servidor de aplicativo.
  
9. Na página **definir a loja do SQL Server Store** , ao definir a loja do SQL Server para o arquivamento e o monitoramento do Skype for Business Server, selecione a instância do SQL Server criada anteriormente para o Skype for business Server 2019. 
  
10. Para publicar sua topologia, clique com o botão direito do mouse no nó do **servidor do Skype for Business** e, em seguida, clique em **publicar topologia**.
  
11. Quando o processo de publicação for concluído, clique em **concluir**.

12. Antes de passar para a próxima seção chamada "verificar a coexistência do pool piloto com o pool herdado", você precisa instalar o novo pool piloto do Skype for Business Server que acabamos de definir na topologia publicada, siga os procedimentos descritos aqui [instalar o Skype para Business Server em servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Uma vez concluída a etapa anterior, vá para a próxima seção para verificar a coexistência do pool piloto com o pool herdado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

