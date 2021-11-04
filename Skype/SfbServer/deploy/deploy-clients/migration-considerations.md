---
title: Skype Considerações sobre a migração do Sistema de Sala
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber como implantar o Skype Room System em um ambiente que tenha várias versões do Skype for Business Server e do Lync Server.
ms.openlocfilehash: f3a26b630873bad0d3c8585486c91c7250f452e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769729"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Considerações sobre a migração do Sistema de Sala
 
Leia este tópico para saber como implantar o Skype Room System em um ambiente que tenha várias versões do Skype for Business Server e do Lync Server.
  
## <a name="migration-considerations"></a>Considerações de migração

Esta seção fornece orientações se você estiver implantando o Skype Room System em um ambiente de vários pools que inclui diferentes versões do Skype for Business Server ou do Lync Server. 
  
O componente replicador de usuário (UR) no Lync Server obtém objetos do usuário do Active Directory e os coloca no banco de dados de back-end do Lync Server SQL Server. Somente a UR no Lync Server 2013 está ciente Skype objetos do Sistema de Sala. A UR nas versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam objetos LRS e, portanto, não estava ciente deles. 
  
Se uma conta do sistema de sala Skype tentar entrar no Lync e executar a descoberta automática com base no registro SRV ou no registro DNS A, e se essas contas apontarem para uma versão anterior do Lync Server ou do Office Communications Server, o LRS receberá uma resposta 404 Not Found do pool herdado. O pool herdado não poderá redirecionar o Skype Room System para seu pool lync Server 2013. 
  
Você pode resolver esse problema com as seguintes opções: 
  
- Aponte seu registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.
    
- Se a primeira opção não for possível, você deverá configurar manualmente o LRS e fornecer o endereço do pool do Lync Server 2013 configurando-o diretamente no aplicativo de console do sistema de sala Skype. 
    
- Se Skype Room System for implantado fora da rede corporativa e um Servidor de Borda do Lync tiver sido implantado e configurado para apontar para um pool ou diretor herdado, será necessário um site secundário do Servidor de Borda, que aponta para o pool do Lync Server 2013. Consulte a documentação de implantação do Servidor de Borda para obter mais informações sobre como implantar um Servidor de Borda secundário. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Interoperabilidade do Sistema de Sala com um Pool do Lync Server 2010

Durante a migração, se um usuário que está em um pool do Lync Server 2010 agendar uma reunião e convidar a conta do sistema de sala do Skype, o cliente do sistema de sala do Skype terá funcionalidade limitada durante a reunião. 
  
Quando o cliente Skype Room System ins junta uma chamada de conferência agendada que foi organizada por um usuário no Lync Server 2010, o Skype Room System tem as seguintes limitações na reunião: 
  
- Skype O Sistema de Sala não pode mostrar a galeria de vídeo com vários visualizações.
    
- Se o Skype do sistema de sala for o apresentador, ele não poderá aplicar o bloqueio de vídeo aos participantes.
    
- Skype O Sistema de Sala não pode mostrar a resolução de vídeo 1080p (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permitir isso, devido ao seguinte: 
    
  - O Lync Server 2010 não dá suporte à resolução 1080p.
    
  - Skype O Sistema de Sala é sempre limitado pela política de conferência do organizador para resolução de vídeo. Portanto, mesmo que o pool do Lync 2010 dê suporte à resolução 720p, o Skype Room System não poderá tirar proveito da resolução 720p, desde que a política do organizador não a suporte. 
    
- Os clientes do Lync 2013 detectam a presença de LRS na sala de reunião e fazem o mudo automático para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.
    
- Há limitações no desempenho de compartilhamento de área de trabalho para reuniões hospedadas no Lync Server 2010.
    
- Os usuários não poderão participar de reuniões privadas (restritas) hospedadas no Lync 2010 com o Skype Room System.
    

