---
title: Considerações sobre migração do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leia este tópico para saber mais sobre como implantar o sistema de sala Skype em um ambiente que possui várias versões do Skype para Business Server e o Lync Server.
ms.openlocfilehash: f5e33c36b0c6a58d83f22e5c18f4de34ffb9d648
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895213"
---
# <a name="skype-room-system-migration-considerations"></a>Considerações sobre migração do Sistema de Salas do Skype
 
Leia este tópico para saber mais sobre como implantar o sistema de sala Skype em um ambiente que possui várias versões do Skype para Business Server e o Lync Server.
  
## <a name="migration-considerations"></a>Considerações sobre migração

Esta seção fornece orientação se você estiver implantando o sistema de sala Skype em um ambiente de várias pool que inclui versões diferentes do Skype para Business Server ou o Lync Server. 
  
O componente User Replicator (UR) no Lync Server obtém objetos de usuário do Active Directory e os coloca no back-end do Lync Server. Somente o UR no Lync Server 2013 está ciente dos objetos do sistema do Skype sala. O UR em versões anteriores do Lync Server e do Office Communications Server não detecta os atributos do Active Directory que designam os objetos LRS e, portanto, não tinha conhecimento deles. 
  
Se uma conta do sistema do Skype sala tenta entrar no Lync e realiza a descoberta automática com base no registro SRV ou aparência de registro DNS A para cima, e essas contas apontem para uma versão anterior do Lync Server ou o Office Communications Server, LRS receberá uma resposta não encontrado 404 do  o pool herdado. O pool herdado não poderão redirecionar o sistema de sala Skype para seu pool doméstico do Lync Server 2013. 
  
Você pode resolver este problema com as seguintes opções: 
  
- Nomeie o registro SRV de descoberta automática (_sipinternaltls._tcp.contoso.com) para o pool do Lync Server 2013.
    
- Se a primeira opção não for possível, você deve configurar LRS manualmente e forneça o endereço de pool do Lync Server 2013 definindo-lo diretamente no aplicativo de console do sistema de sala do Skype. 
    
- Se o sistema de sala do Skype for implantado fora da rede corporativa e um servidor de borda do Lync foi implantado e configurado para apontar para um pool herdado ou diretor, um site secundário do servidor de borda será necessário, que aponta para o pool do Lync Server 2013. Consulte a documentação de implantação do Edge Server para obter mais informações sobre a implantação de um Edge Server secundário. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilidade de sistema do Skype sala com um Pool do Lync Server 2010

Durante a migração, se um usuário hospedado em um pool do Lync Server 2010 agenda uma reunião e convida a conta de sistema do Skype sala, cliente do sistema de sala Skype será têm recursos limitados ao participar da reunião. 
  
Quando o cliente do sistema de sala Skype ingressa em uma chamada em conferência agendada que foi organizada por um usuário hospedado no Lync Server 2010, o sistema de sala Skype tem as seguintes limitações de reunião: 
  
- Sistema de sala Skype não é possível exibir a Galeria de vídeo com multi-view.
    
- Se o cliente do sistema de sala Skype for o apresentador, ele não é possível aplicar o bloqueio de vídeo em participantes.
    
- Sistema de sala Skype não é possível exibir 1080p resolução de vídeo (entrada ou saída), mesmo se a política de conferência do Lync Server 2013 permite que ele, devido a estes motivos: 
    
  - Lync Server 2010 não oferece suporte a resolução de 1080p.
    
  - Sistema de sala Skype sempre é limitado pela política de conferência do organizador para resolução de vídeo. Portanto, mesmo se o pool do Lync 2010 oferece suporte a resolução 720 pixels, Skype sala sistema não será capaz de aproveitar resolução 720 pixels desde que ele não oferece suporte a política do organizador. 
    
- Os clientes do Lync 2013 detectam a presença de LRS na sala de reunião e eles são silenciados automaticamente para evitar eco na sala de reunião física. Esse recurso não funciona em reuniões hospedadas no Lync Server 2010.
    
- Existem limites quanto ao desempenho de compartilhamento da área de trabalho para reuniões hospedadas no Lync Server 2010.
    
- Os usuários não poderão ingressar em particulares (restritas) reuniões hospedadas no Lync 2010 com o sistema de sala Skype.
    

