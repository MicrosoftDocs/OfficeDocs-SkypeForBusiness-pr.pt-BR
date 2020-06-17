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
description: Uma das primeiras etapas necessárias para a migração para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Skype for Business Server 2019.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752853"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implantar o pool piloto do Skype for Business Server 2019

Uma das primeiras etapas necessárias para a migração para o Skype for Business Server 2019 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Skype for Business Server 2019 com sua implantação herdada. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Skype for Business Server 2019. 
  
Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends. Você deve implantar os mesmos recursos e cargas de trabalho em seu pool piloto do Skype for Business Server 2019 que você tem em seu pool herdado. Se você implantou o servidor de arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento de seu ambiente herdado e deseja continuar arquivando ou monitorando durante a migração, também é necessário implantar esses recursos no seu ambiente piloto. A versão implantada para arquivar ou monitorar seu ambiente herdado não capturará dados no seu ambiente do Skype for Business Server 2019. 
  
> [!NOTE]
> O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implantar um pool piloto do Skype for Business Server 2019

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
2. Expanda a árvore até atingir os pools de front-ends **do Skype for Business Server 2019**  >  **Enterprise Edition**.
    
3. Clique com o botão direito em **pools de front-ends Enterprise Edition** e selecione **novo pool de front-ends**.
  
4. Insira o nome de domínio totalmente qualificado (FQDN) do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-ends Enterprise Edition ou um servidor Standard Edition. O Skype for Business Server 2019 não exige que os recursos do pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    > [!CAUTION]
    > O pool ou FQDN do servidor que você define para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool herdado atualmente implantado ou de qualquer outro servidor atualmente implantado. 
  
5. Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se você estiver implantando apenas recursos de mensagens instantâneas (IM) e presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas você não selecionará as caixas de seleção conferência de discagem (PSTN), Enterprise Voice ou controle de admissão de chamada, pois representam recursos de voz, vídeo e conferência colaborativa. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. Na página **selecionar funções de servidor posicionadas** , recomendamos que você escolha colocar o servidor de mediação no Skype for Business Server 2019. Ao mesclar uma topologia herdada com o Skype for Business Server 2019, exige que você primeiro coloque o servidor de mediação herdado. Após mesclar as topologias e configurar o servidor de mediação do Skype for Business Server 2019, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo quando mover a função de servidor de mediação para o Skype for Business Server 2019 mais tarde no processo de implantação. 
   
7. Na página **associar funções de servidor a este pool de front-ends** , durante a implantação do pool piloto, *não* escolha o **pool habilitar um pool de borda a ser usado pelo componente de mídia dessa opção de pool de front-ends** . Esse é um recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto. 
  
8. Na página**Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.
  
9. Na página **definir o repositório de arquivamento do SQL Server** , ao definir o repositório do SQL Server para o arquivamento e monitoramento do Skype for Business Server, selecione a instância do SQL Server criada anteriormente para o Skype for business Server 2019. 
  
10. Para publicar sua topologia, clique com o botão direito do mouse no nó do **Skype for Business Server** e clique em **publicar topologia**.
  
11. Quando o processo de publicação for concluído, clique em **Finalizar**.

12. Antes de passar para a próxima seção chamada "verificar a coexistência do pool piloto com o pool herdado", você precisa instalar o novo pool piloto de front-ends do Skype for Business Server que acabamos de definir na topologia publicada, siga os procedimentos descritos aqui [instalar o Skype for Business Server em servidores na topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Após a conclusão da etapa anterior, vá para a próxima seção para verificar a coexistência do pool piloto com o pool herdado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

