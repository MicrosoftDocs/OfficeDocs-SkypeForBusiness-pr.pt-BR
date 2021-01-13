---
title: Planejar o Atendimento de Chamadas em Grupo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planejamento do Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente destinadas a outras pessoas.
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825611"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planejar o Atendimento de Chamadas em Grupo no Skype for Business
 
Planejamento do Atendimento de Chamadas em Grupo no Skype for Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente destinadas a outras pessoas.
  
O Recebimento de Chamadas em Grupo permite que os usuários atendam a chamadas de entrada para seus colegas em seus próprios telefones. Isso aumenta a disponibilidade da linha de um usuário, permitindo que outros usuários atendam a uma chamada de entrada discando um número de grupo de atendimento de chamadas. Quando o Recebimento de Chamadas em Grupo é implantado, o número de chamadas de entrada roteadas para a caixa postal pode ser reduzido significativamente, o que é particularmente útil para chamadas de clientes externos à sua organização.
  
O recurso de Atendimento de Chamada em Grupo foi projetado especialmente para unidades de negócios em ambientes de escritório aberto. As chamadas de entrada não são interrupções porque toam apenas no destino pretendido. No entanto, outros usuários que ouvem o toque ainda podem atender a chamada simplesmente discando o número do grupo. 
  
Em ambientes onde os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum são geograficamente distribuídos, a chamada de equipe apresenta a solução mais adequada. A principal diferença entre o Recebimento de Chamadas em Grupo e a chamada de equipe é que, com o Recebimento de Chamadas em Grupo, uma chamada de entrada toca apenas no destino pretendido, mas qualquer pessoa ainda pode optar por respondê-la discando um número de grupo. Com a chamada em equipe, a chamada toca em todos os telefones dos membros da equipe, e qualquer usuário da equipe pode atender ao telefone para atender a chamada. Uma diferença adicional entre o Atendimento de Chamadas em Grupo e a chamada de equipe é que o Atendimento de Chamadas em Grupo é gerenciado por um administrador, por meio do Skype for Business Server. Com a chamada em equipe, os usuários finais gerenciam o recurso usando o cliente Skype for Business. Com o Atendimento de Chamada em Grupo, portanto, esse aspecto do gerenciamento de chamada pode ser centralizado.
  
O Atendimento de Chamada em Grupo é criado no aplicativo Estacionamento de Chamada. Ao implantar o Atendimento de Chamada em Grupo, você configura a tabela de órbita de estacionamento de chamada com intervalos separados de ramais designados como números de grupo de atendimento de chamada. Assim como os números de órbita de estacionamento de chamada, os números do grupo de atendimento de chamadas devem ser ramais virtuais que não têm nenhum usuário ou telefone atribuído a eles. Cada pool de Front End onde você implanta o Atendimento de Chamada em Grupo pode ter um ou mais intervalos de números de grupo de atendimento de chamada. Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Skype for Business Server. 
  
> [!NOTE]
> Os intervalos de números designados como números de Atendimento de Chamadas em Grupo na tabela de órbita de estacionamento de chamadas não podem ser gerenciados ou exibidos usando o Painel de Controle do Skype for Business Server. A única maneira de ver todos os intervalos de números na tabela de órbita de estacionamento de chamadas é usar o Shell de Gerenciamento do Skype for Business Server. Da mesma forma, a única maneira de adicionar, modificar ou remover números de Atendimento de Chamadas em Grupo é usar o Shell de Gerenciamento do Skype for Business Server. 
  
Depois de configurar os números do grupo de atendimento de chamada, você atribui usuários a um grupo de atendimento de chamada. Qualquer usuário atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega para um usuário que está atribuído a um grupo de atendimento de chamada, qualquer outro usuário que perceba a chamada pode atender a ela discando manualmente o número do grupo de atendimento de chamada. O usuário que atende a chamada não precisa ser membro do grupo. Quando uma chamada é a escolhida por outro usuário, uma notificação é enviada para o número originalmente chamado.
  
> [!NOTE]
> Um usuário pode ser membro de apenas um grupo de atendimento de chamada. 
  
> [!NOTE]
> Embora qualquer usuário na implantação do Skype for Business Server possa atender a uma chamada para um membro do grupo de atendimento de chamadas, a pessoa que atende a chamada deve saber o número correto do grupo de atendimento de chamadas para discar. 
  
Se um usuário discar para um número de grupo de atendimento de chamada para atender a uma chamada quando vários telefones do grupo tocarem, o usuário atenderá à chamada que está tocando por mais tempo.
  
As configurações de toque simultâneo funcionarão para usuários com atendimento de chamada em grupo. Ou seja, uma chamada feita a um usuário que tem o Atendimento de Chamada em Grupo tocará para todos os destinos configurados e outro usuário poderá atender à chamada. A exceção a essa regra é quando o usuário configura o toque simultâneo para chamar todos os membros da equipe.
  
O Atendimento de Chamadas em Grupo não pode ser usado para atender aos seguintes tipos de chamadas:
  
- Chamadas para uma linha privada
    
- Chamadas de um contato que recebeu a relação de privacidade Amigos e Família
    
    > [!TIP]
    > Um usuário que seja membro de um grupo de atendimento de chamadas pode impedir que determinadas chamadas seja recuperadas por meio do Atendimento de Chamadas em Grupo marcando o contato como um contato pessoal no cliente Skype for Business. Para marcar um contato como um contato pessoal, de definida a Relação de Privacidade do contato como Amigos e Família. Qualquer chamada de entrada de contatos com a Relação de Privacidade definida como Amigos e Família não pode ser recuperada usando o Recebimento de Chamadas em Grupo. 
  
- Parte de vídeo de chamadas de áudio/vídeo 
    
    > [!NOTE]
    > Se um usuário atender a uma chamada de áudio/vídeo, ele receberá apenas o áudio. A pessoa que liga ou a pessoa que atende a chamada pode escalonar a chamada para adicionar vídeo. 
  
- Chamadas de toque simultâneo que são roteados para membros da chamada de equipe
    
- Chamadas roteados para um representante
    
- Chamadas roteados para um grupo de resposta
    
Os tipos de usuários a seguir não podem participar do Atendimento de Chamada em Grupo. Ou seja, eles não devem ser incluídos em um grupo de Atendimento de Chamadas em Grupo e não podem atender chamadas para usuários que tenham o Atendimento de Chamadas em Grupo habilitado.
  
- Usuários que estão online em uma implantação híbrida
    
- Usuários que não estão em um pool do Skype for Business Server 2015 ou em um pool do Lync Server 2013 com Atualizações Cumulativas para Lync Server 2013: fevereiro de 2013 em uma implantação local
    
Se ninguém atender a uma chamada para um membro de um grupo de atendimento de chamada, a chamada será roteada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para a caixa postal ou é encaminhada para um destino diferente, conforme especificado nas configurações do cliente.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O Atendimento de Chamadas em Grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo Estacionamento de Chamadas. Você habilita o Atendimento de Chamada em Grupo configurando a tabela de órbita de Estacionamento de Chamada com intervalos separados de números designados como números de grupo de atendimento de chamada e, em seguida, atribuindo usuários a grupos de atendimento de chamada e habilitando os usuários para o Atendimento de Chamada em Grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes com suporte para o Atendimento de Chamada em Grupo

Qualquer um dos seguintes clientes pode ser usado para atender chamadas para membros de Atendimento de Chamadas em Grupo:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Os usuários podem usar qualquer um desses clientes para atender chamadas para membros de Atendimento de Chamadas em Grupo, mas eles devem estar em um pool do Skype for Business Server ou em um pool do Lync Server 2013 com Atualizações Cumulativas para Lync Server 2013: fevereiro de 2013. 
  
Os seguintes clientes e dispositivos não são suportados para atender chamadas para membros de Atendimento de Chamadas em Grupo:
  
- Lync Mobile
    
- Aplicativo Lync para Windows 8 e Windows RT
    
- Lync para iPad
    
- Telefones analógicos
    
- Telefones com números PSTN (rede telefônica pública comutado)
    
## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário de Atendimento de Chamada em Grupo que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> O Atendimento de Chamada em Grupo é baseado no aplicativo Estacionamento de Chamada. Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de Estacionamento de Chamada, incluindo o Atendimento de Chamada em Grupo, em ambos os pools. 
  
**Modelo de usuário de atendimento de chamada em grupo**

|**Indicador**|**Por pool de front-end  <br/>  (com 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Número recomendado de usuários por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuários por pool habilitado para o Atendimento de Chamada em Grupo  <br/> |25.000  <br/> |3,000  <br/> |
|Taxa máxima de chamadas de entrada para o total de usuários habilitados para Recebimento de Chamadas em Grupo por pool por minuto  <br/> |500  <br/> |60  <br/> |
|Taxa máxima de chamadas recuperadas por usuários com Atendimento de Chamadas em Grupo por pool por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para pools de front-end com menos de oito Servidores front-end, calcule as métricas linearmente. Por exemplo, se seu pool de Front-End tiver um Servidor Front-End, calcule a carga máxima como 1/8 dos valores mostrados na tabela. 
  
> [!NOTE]
> Você pode aumentar ou diminuir o número recomendado de usuários por grupo e o número de grupos, desde que não exceda o número máximo de usuários por pool. Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o Atendimento de Chamada em Grupo ainda está dentro do máximo do modelo de usuário (ou seja, 120 grupos vezes 25 usuários é 3.000 usuários habilitados para o Atendimento de Chamada em Grupo). 
  

