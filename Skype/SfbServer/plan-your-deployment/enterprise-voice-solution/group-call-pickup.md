---
title: Planejar a retirada de chamada do grupo no Skype for Business
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planejamento de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente pretendidas para outras pessoas.
ms.openlocfilehash: 17c3d453fa54ea72c02c022d33b0b2f1c61e8b0b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016195"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planejar a retirada de chamada do grupo no Skype for Business
 
Planejamento de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente pretendidas para outras pessoas.
  
Atendimento de chamada de grupo permite aos usuários atender chamadas de entrada para seus colegas de suas próprias telefones. Esse novo recurso aumenta a disponibilidade da linha de usuário ao permitir que outros usuários atendam uma chamada em entrada discando um número de grupo de atendimento de chamadas. Quando o atendimento de chamada de grupo estiver implantado, o número de chamadas de entrada que são roteadas para a caixa postal pode ser significativamente reduzido, que é particularmente útil para as chamadas dos clientes que são externos à sua organização.
  
O recurso de atendimento de chamada de grupo foi projetado especificamente para unidades de negócios em ambientes do office open. Chamadas de entrada não perturbam porque tocam somente no destino desejado. Porém, outros usuários que escutam o toque podem atender a chamada simplesmente discando o número de grupo de atendimento de chamadas. 
  
Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum estão espalhados geograficamente, a chamada em equipe apresenta-se como a solução mais adequada. A principal diferença entre o atendimento de chamada de grupo e chamada de equipe é que, com atendimento de chamada de grupo, uma chamada de entrada toca apenas no destino pretendido, mas ninguém ainda pode optar atendê-la, discando um número de grupo. Com chamada em equipe, a chamada toca nos telefones de todos os membros da equipe e qualquer usuário na equipe pode atender o telefone para responder à chamada. Uma diferença adicional entre o atendimento de chamada de grupo e chamada de equipe é que o atendimento de chamada do grupo é gerenciado por um administrador, por meio do Skype para Business Server. Com a chamada de equipe, os usuários finais gerenciar o recurso usando o Skype para o cliente de negócios. Portanto, com atendimento de chamada de grupo, esse aspecto do gerenciamento de chamada pode ser centralizado.
  
Atendimento de chamada de grupo é criado no aplicativo de estacionamento de chamadas. Quando você implanta o atendimento de chamada de grupo, você configura a tabela de órbita de estacionamento de chamada com separado intervalos de números de ramal que forem designados como números de retirada de grupo de chamada. Como os números de órbita de estacionamento de chamadas, os números de grupo de atendimento de chamadas precisam ser extensões virtuais que não têm um usuário ou telefone atribuídos a elas. Cada pool de Front-End, onde você implanta o atendimento de chamada do grupo pode ter um ou mais intervalos de números de retirada de grupo de chamada. Os intervalos de números de grupo devem ser exclusivos entre o Skype para implantação de servidor de negócios. 
  
> [!NOTE]
> Intervalos de número que são designados como números de atendimento de chamada de grupo na tabela de órbita de estacionamento de chamada não podem ser gerenciados ou exibidos usando o Skype para painel de controle do servidor de negócios. A única maneira para ver todos os intervalos de números na tabela de órbita de estacionamento de chamada é usar Skype do Shell de gerenciamento do servidor de negócios. Da mesma forma, a única maneira de adicionar, modificar ou remover os números de atendimento de chamada do grupo é usar Skype do Shell de gerenciamento do servidor de negócios. 
  
Após você configurar os números de grupos de atendimento de chamadas, você atribui usuários a um grupo de atendimento de chamadas. Qualquer usuário que for atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega para um usuário atribuído a um grupo de atendimento de chamadas, qualquer outro usuário que perceba a chamada pode atendê-la manualmente discando o número de grupo de atendimento de chamadas. O usuário que atender a chamada não precisa ser um membro do grupo. Quando uma chamada é atendida por outro usuário, uma notificação é enviada ao número que foi chamado originalmente.
  
> [!NOTE]
> Um usuário pode ser membro de somente um grupo de atendimento de chamadas. 
  
> [!NOTE]
> Embora a qualquer usuário no Skype para implantação de servidor de negócios pode atender uma chamada para um membro do grupo de retirada de chamada, a pessoa pode atender a chamada deve saber o número de retirada de grupo de chamada correta para discar. 
  
Se um usuário discar um número de grupo de atendimento de chamadas para atender uma chamada quando diversos telefones no grupo estiverem tocando, o usuário atenderá a chamada que estiver tocando a mais tempo.
  
Configurações de toque simultâneo funcionarão para usuários habilitados para atendimento de chamadas em grupo. Ou seja, uma chamada feita para um usuário que tem o atendimento de chamada do grupo tocarão para todos os destinos configurados, e outro usuário pode atender a chamada. A exceção para essa regra é quando o usuário configura toque simultâneo para todos os membros da equipe.
  
Atendimento de chamada de grupo não pode ser usado para atender os seguintes tipos de chamadas:
  
- Chamadas a uma linha privada
    
- Chamadas de um contato ao qual foi atribuída a política de privacidade Amigos e Família
    
    > [!TIP]
    > Um usuário que seja membro de um grupo de chamada retirada pode impedir que certos chamadas sejam recuperadas por meio de atendimento de chamada do grupo, marcando o contato como um contato pessoal no Skype para o cliente de negócios. Para marcar um contato como seu contato pessoal, defina a Relação de Privacidade para o contato como Amigos e Família. Qualquer chamada de entrada de contatos com a relação de privacidade definido como amigos e família não pode ser recuperada usando o atendimento de chamada do grupo. 
  
- Porção de vídeo de chamadas de áudio/vídeo 
    
    > [!NOTE]
    > Se um usuário responde uma chamada de áudio/vídeo, ele recebe somente o áudio. Tanto a pessoa que realizou a chamada quanto a que está recebendo podem escalar a chamada para adicionar o vídeo. 
  
- Chamadas de toque simultâneo que são direcionada para membros da equipe de atendimento de chamadas
    
- Chamadas direcionadas a um representante
    
- Chamadas direcionadas a um grupo de resposta
    
Os seguintes tipos de usuários não podem participar de atendimento de chamada do grupo. Ou seja, não devem ser incluídos em um grupo de atendimento de chamada de grupo e eles não podem pegue chamadas para usuários que possuem o atendimento de chamada de grupo habilitado.
  
- Usuários que estão hospedados em uma implantação híbrida
    
- Os usuários que não estão hospedados em qualquer um Skype para Business Server 2015 pool ou um pool do Lync Server 2013 com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 em uma implantação local
    
Se ninguém responder uma chamada destinada a um membro de um grupo de atendimento de chamadas, ela é direcionada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para correio de voz e ou é direcionada para um outro destino, conforme estiver especificado nas configurações do cliente.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

Atendimento de chamada do grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo de estacionamento de chamadas. Habilitar o atendimento de chamada do grupo, definindo a tabela de órbita de estacionamento de chamada com separado intervalos de números designados como números de retirada de grupo de chamada e, em seguida, atribuindo os usuários chamem grupos de retirada e habilitar os usuários para atendimento de chamada do grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes com suporte para atendimento de chamada de grupo

Qualquer um dos seguintes clientes pode ser usado para atender a chamadas para os membros de atendimento de chamada de grupo:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Os usuários podem usar qualquer um destes clientes para atender a chamadas para os membros de atendimento de chamada do grupo, mas os usuários devem ser hospedados em um Skype para pool de servidores de negócios ou de um pool do Lync Server 2013 com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013. 
  
Os seguintes clientes e dispositivos, não há suporte para a separação de chamadas para os membros de atendimento de chamada de grupo:
  
- Lync Mobile
    
- Aplicativo do Lync para Windows 8 e Windows RT
    
- Lync para iPad
    
- Telefones analógicos
    
- Telefones com números de PSTN (Rede Telefônica Pública Comutada)
    
## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário de atendimento de chamada do grupo que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> Atendimento de chamada do grupo é baseado no aplicativo de estacionamento de chamadas. Tenha em mente que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool pareado deve ser capaz de manipular cargas de trabalho para os serviços de estacionamento de chamada, incluindo o atendimento de chamada de grupo, em ambos os pools. 
  
**Modelo de usuário retirada de chamada de grupo**

|**Métrica**|**Por pool de Front-End <br/> (com 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Número recomendado de usuários por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuários por pool ativado para Recebimento de chamada de grupo  <br/> |25.000  <br/> |3.000  <br/> |
|Taxa máxima de chamadas recebidas para o total de usuários habilitados para Recebimento de chamada de grupo por pool por minuto  <br/> |500  <br/> |60  <br/> |
|Taxa máxima de chamadas recuperadas por usuários com Recebimento de chamada de grupo por pool por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para pools de Front-End que possuem menos de oito servidores Front-End, calcule as métricas linearmente. Por exemplo, se o seu pool de Front-End tem um servidor Front-End, calcule a carga máxima como 1/8 dos valores mostrados na tabela. 
  
> [!NOTE]
> Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos desde que você não exceda o número máximo de usuários por pool. Por exemplo, o servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o atendimento de chamada do grupo ainda está dentro o máximo de modelo de usuário (ou seja, ocasiões 120 grupos é de 25 usuários 3.000 usuários habilitados para o atendimento de chamada de grupo). 
  

