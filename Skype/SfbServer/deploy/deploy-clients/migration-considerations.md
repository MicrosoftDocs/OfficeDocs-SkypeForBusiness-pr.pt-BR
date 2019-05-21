---
title: Considerações sobre migração do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber mais sobre como implantar o sistema de sala do Skype em um ambiente com várias versões do Skype for Business Server e do Lync Server.
ms.openlocfilehash: 35dd7cff34134791ebaf62bf4d0fcd1cf3b83a4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293519"
---
# <a name="skype-room-system-migration-considerations"></a>Considerações sobre migração do Sistema de Salas do Skype
 
Leia este tópico para saber mais sobre como implantar o sistema de sala do Skype em um ambiente com várias versões do Skype for Business Server e do Lync Server.
  
## <a name="migration-considerations"></a>Considerações sobre migração

Esta seção fornece orientação se você estiver implantando o sistema de sala da Skype em um ambiente com vários pools que inclua versões diferentes do Skype for Business Server ou do Lync Server. 
  
O componente User Replicator (UR) no Lync Server obtém objetos de usuário do Active Directory e os coloca no back-end do Lync Server. Somente o UR no Lync Server 2013 reconhece os objetos do sistema de sala do Skype. O UR em versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam os objetos LRS e, portanto, não tinha conhecimento deles. 
  
Se uma conta do sistema de sala do Skype tentar entrar no Lync e executar a descoberta automática com base no registro SRV ou DNS A procurar por um registro e se essas contas apontarem para uma versão anterior do Lync Server ou Office Communications Server, o LRS receberá uma resposta do 404 não encontrada do  o pool herdado. O pool herdado não poderá redirecionar o sistema de sala da Skype para o pool Home do Lync Server 2013. 
  
Você pode resolver este problema com as seguintes opções: 
  
- Nomeie o registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.
    
- Se a primeira opção não for possível, você deve configurar manualmente o LRS e fornecer o endereço do pool do Lync Server 2013, configurando-o diretamente no aplicativo de console do sistema de sala do Skype. 
    
- Se o sistema de salas da Skype for implantado fora da rede corporativa e um servidor de borda do Lync tiver sido implantado e configurado para apontar para um pool ou diretor herdado, será necessário um site de servidor de borda secundário que aponte para o pool do Lync Server 2013. Consulte a documentação de implantação do Edge Server para obter mais informações sobre a implantação de um Edge Server secundário. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidade do sistema de sala do Skype com um pool do Lync Server 2010

Durante a migração, se um usuário que estiver hospedado em um pool do Lync Server 2010 agendar uma reunião e convidar a conta do sistema de sala do Skype, o cliente do sistema da sala do Skype terá funcionalidade limitada enquanto participará da reunião. 
  
Quando o cliente do sistema de sala do Skype ingressa em uma chamada em conferência programada que foi organizada por um usuário hospedado no Lync Server 2010, o sistema de sala do Skype tem as seguintes limitações na reunião: 
  
- O sistema de sala da Skype não pode mostrar a Galeria de vídeos de várias exibições.
    
- Se o cliente do sistema de sala do Skype for o apresentador, ele não poderá aplicar bloqueio de vídeo aos participantes.
    
- O sistema de sala da Skype não pode mostrar a resolução de vídeo de 1080p (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permitir, devido ao seguinte: 
    
  - O Lync Server 2010 não é compatível com a resolução de 1080p.
    
  - O sistema de sala do Skype é sempre limitado pela política de conferência do organizador para resolução de vídeo. Portanto, mesmo que o pool do Lync 2010 dê suporte à resolução de 720p, o sistema de sala da Skype não poderá tirar proveito da resolução de 720p, desde que a política do organizador não seja compatível. 
    
- Os clientes do Lync 2013 detectam a presença de LRS na sala de reunião e eles são silenciados automaticamente para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.
    
- Existem limites quanto ao desempenho de compartilhamento da área de trabalho para reuniões hospedadas no Lync Server 2010.
    
- Os usuários não poderão ingressar em reuniões privadas (restritas) hospedadas no Lync 2010 com o sistema de sala do Skype.
    

