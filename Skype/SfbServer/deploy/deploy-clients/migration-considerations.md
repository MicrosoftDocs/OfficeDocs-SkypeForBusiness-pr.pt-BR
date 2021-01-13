---
title: Considerações sobre a migração do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber mais sobre como implantar o Sistema de Sala do Skype em um ambiente que tem várias versões do Skype for Business Server e do Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805781"
---
# <a name="skype-room-system-migration-considerations"></a>Considerações sobre a migração do Sistema de Sala do Skype
 
Leia este tópico para saber mais sobre como implantar o Sistema de Sala do Skype em um ambiente que tem várias versões do Skype for Business Server e do Lync Server.
  
## <a name="migration-considerations"></a>Considerações de migração

Esta seção fornece orientações se você estiver implantando o Sistema de Sala do Skype em um ambiente de vários pools que inclui versões diferentes do Skype for Business Server ou do Lync Server. 
  
O componente Replicador de usuários (UR) no Lync Server obtém objetos de usuário do Active Directory e os coloca no banco de dados do SQL Server back-end do Lync Server. Somente o UR no Lync Server 2013 está ciente dos objetos do Sistema de Sala do Skype. O UR em versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam objetos LRS e, portanto, não tinha conhecimento deles. 
  
Se uma conta do Sistema de Sala do Skype tentar entrar no Lync e realizar a descoberta automática com base no registro SRV ou na pesquisa do registro DNS A, e se essas contas apontarem para uma versão anterior do Lync Server ou do Office Communications Server, o LRS receberá uma resposta 404 Não Encontrado do pool herdado. O pool herdado não poderá redirecionar o Sistema de Sala do Skype para seu pool Lync Server 2013. 
  
Você pode resolver esse problema com as seguintes opções: 
  
- Aponte seu registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.
    
- Se a primeira opção não for possível, configure manualmente o LRS e forneça o endereço do pool do Lync Server 2013 configurando-o diretamente no aplicativo de console do Sistema de Sala do Skype. 
    
- Se o Sistema de Sala do Skype for implantado fora da rede corporativa e um Servidor de Borda do Lync tiver sido implantado e configurado para apontar para um pool ou diretor herdado, um site secundário do Servidor de Borda será necessário, que aponta para o pool do Lync Server 2013. Consulte a documentação de implantação do Servidor de Borda para obter mais informações sobre como implantar um Servidor de Borda secundário. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidade do sistema de sala do Skype com um pool do Lync Server 2010

Durante a migração, se um usuário que está em um pool do Lync Server 2010 agendar uma reunião e convidar a conta do Sistema de Sala do Skype, o cliente do Sistema de Sala do Skype terá funcionalidade limitada ao participar da reunião. 
  
Quando o cliente do Sistema de Sala do Skype participa de uma chamada agendada em conferência organizada por um usuário no Lync Server 2010, o Sistema de Sala do Skype tem as seguintes limitações de reunião: 
  
- O Sistema de Sala do Skype não pode mostrar a galeria de vídeos com várias exibições.
    
- Se o cliente do Sistema de Sala do Skype for o apresentador, ele não poderá aplicar bloqueio de vídeo aos participantes.
    
- O Sistema de Sala do Skype não pode mostrar a resolução de vídeo de 1080p (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permitir, devido ao seguinte: 
    
  - O Lync Server 2010 não dá suporte à resolução de 1080p.
    
  - O Sistema de Sala do Skype é sempre limitado pela política de conferência do organizador para resolução de vídeo. Portanto, mesmo que o pool do Lync 2010 dê suporte à resolução de 720p, o Sistema de Sala do Skype não poderá aproveitar a resolução de 720p, desde que a política do organizador não dê suporte a ele. 
    
- Os clientes do Lync 2013 detectam a presença do LRS na sala de reunião e fazem o mudo automático para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.
    
- Há limitações no desempenho de compartilhamento de área de trabalho para reuniões hospedadas no Lync Server 2010.
    
- Os usuários não poderão participar de reuniões privadas (restritas) hospedadas no Lync 2010 com o Sistema de Sala do Skype.
    

