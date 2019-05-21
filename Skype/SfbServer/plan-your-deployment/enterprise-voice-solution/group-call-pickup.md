---
title: Planejar o recebimento de chamadas em grupo no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planejando o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente destinadas para outras pessoas.
ms.openlocfilehash: c729e2d672d104337820c44fa41c113dded3110f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276835"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planejar o recebimento de chamadas em grupo no Skype for Business
 
Planejando o recebimento de chamadas em grupo no Skype for Business Server Enterprise Voice, que permite aos usuários atender chamadas originalmente destinadas para outras pessoas.
  
O recurso de recebimento de chamadas em grupo permite que os usuários atendam às chamadas de entrada para seus colegas a partir dos próprios telefones. Esse novo recurso aumenta a disponibilidade da linha de usuário ao permitir que outros usuários atendam uma chamada em entrada discando um número de grupo de atendimento de chamadas. Quando o recebimento de chamadas em grupo é implantado, o número de chamadas de entrada direcionadas para o correio de voz pode ser reduzido significativamente, o que é especialmente útil para chamadas de clientes externos à sua organização.
  
O recurso de recebimento de chamadas em grupo foi projetado especificamente para unidades de negócios em ambientes abertos do Office. Chamadas de entrada não perturbam porque tocam somente no destino desejado. Porém, outros usuários que escutam o toque podem atender a chamada simplesmente discando o número de grupo de atendimento de chamadas. 
  
Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum estão espalhados geograficamente, a chamada em equipe apresenta-se como a solução mais adequada. A principal diferença entre o recebimento de chamadas em grupo e a chamada de equipe é que, com o recebimento de chamadas em grupo, uma chamada de entrada tocará somente no destino pretendido, mas qualquer pessoa ainda poderá atendê-la ao discar um número de grupo. Com chamada em equipe, a chamada toca nos telefones de todos os membros da equipe e qualquer usuário na equipe pode atender o telefone para responder à chamada. Uma diferença adicional entre o recebimento de chamadas em grupo e a chamada de equipe é que o recebimento de chamadas em grupo é gerenciado por um administrador, por meio do Skype for Business Server. Com a chamada de equipe, os usuários finais gerenciam o recurso usando o cliente Skype for Business. Com o recebimento de chamadas em grupo, esse aspecto do gerenciamento de chamadas pode ser centralizado.
  
O recebimento de chamadas em grupo foi criado no aplicativo de estacionamento de chamadas. Ao implantar o recurso de recebimento de chamadas em grupo, configure a tabela órbita do estacionamento de chamada com intervalos separados de números de ramal designados como números de grupo de retirada de chamadas. Como os números de órbita de estacionamento de chamadas, os números de grupo de atendimento de chamadas precisam ser extensões virtuais que não têm um usuário ou telefone atribuídos a elas. Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamadas. Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Skype for Business Server. 
  
> [!NOTE]
> Os intervalos de números que são designados como números de retirada de chamadas em grupo na tabela do parque da chamada não podem ser gerenciados ou exibidos usando o painel de controle do Skype for Business Server. A única maneira de ver todos os intervalos de números na tabela órbita do estacionamento de chamada é usar o Shell de gerenciamento do Skype for Business Server. Da mesma forma, a única maneira de adicionar, modificar ou remover números de recebimento de chamadas em grupo é usar o Shell de gerenciamento do Skype for Business Server. 
  
Após você configurar os números de grupos de atendimento de chamadas, você atribui usuários a um grupo de atendimento de chamadas. Qualquer usuário que for atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega para um usuário atribuído a um grupo de atendimento de chamadas, qualquer outro usuário que perceba a chamada pode atendê-la manualmente discando o número de grupo de atendimento de chamadas. O usuário que atender a chamada não precisa ser um membro do grupo. Quando uma chamada é atendida por outro usuário, uma notificação é enviada ao número que foi chamado originalmente.
  
> [!NOTE]
> Um usuário pode ser membro de somente um grupo de atendimento de chamadas. 
  
> [!NOTE]
> Embora qualquer usuário na implantação do Skype for Business Server possa atender a uma chamada para um membro do grupo de recebimento de chamadas, a pessoa que atende a chamada precisa saber o número correto de grupo de recebimento de chamadas para discar. 
  
Se um usuário discar um número de grupo de atendimento de chamadas para atender uma chamada quando diversos telefones no grupo estiverem tocando, o usuário atenderá a chamada que estiver tocando a mais tempo.
  
Configurações de toque simultâneo funcionarão para usuários habilitados para atendimento de chamadas em grupo. Ou seja, uma chamada feita para um usuário que tem o recurso de chamada em grupo tocará para todos os destinos configurados e outro usuário poderá atender a chamada. A exceção para essa regra é quando o usuário configura toque simultâneo para todos os membros da equipe.
  
Não é possível usar o recurso de recebimento de chamadas em grupo para atender aos seguintes tipos de chamadas:
  
- Chamadas a uma linha privada
    
- Chamadas de um contato ao qual foi atribuída a política de privacidade Amigos e Família
    
    > [!TIP]
    > Um usuário que é membro de um grupo de recebimento de chamadas pode impedir que determinadas chamadas sejam recuperadas por meio da retirada de chamadas em grupo, marcando o contato como um contato pessoal no cliente Skype for Business. Para marcar um contato como seu contato pessoal, defina a Relação de Privacidade para o contato como Amigos e Família. Qualquer chamada de entrada de contatos com a relação de privacidade definida como amigos e parentes não pode ser recuperada usando a retirada de chamadas em grupo. 
  
- Porção de vídeo de chamadas de áudio/vídeo 
    
    > [!NOTE]
    > Se um usuário responde uma chamada de áudio/vídeo, ele recebe somente o áudio. Tanto a pessoa que realizou a chamada quanto a que está recebendo podem escalar a chamada para adicionar o vídeo. 
  
- Chamadas de toque simultâneo que são direcionada para membros da equipe de atendimento de chamadas
    
- Chamadas direcionadas a um representante
    
- Chamadas direcionadas a um grupo de resposta
    
Os tipos de usuários a seguir não podem participar da retirada de chamadas em grupo. Ou seja, eles não devem ser incluídos em um grupo de recebimento de chamadas em grupo e não podem atender chamadas para usuários que tenham o recurso de recebimento de chamadas em grupo habilitado.
  
- Usuários que estão hospedados em uma implantação híbrida
    
- Os usuários que não são hospedados em um pool do Skype for Business Server 2015 ou no pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013: de fevereiro de 2013 em uma implantação local
    
Se ninguém responder uma chamada destinada a um membro de um grupo de atendimento de chamadas, ela é direcionada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para correio de voz e ou é direcionada para um outro destino, conforme estiver especificado nas configurações do cliente.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O recebimento de chamadas em grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo de estacionamento de chamadas. Você permite o recebimento de chamadas em grupo Configurando a tabela órbita de estacionamento de chamada com intervalos separados de números designados como números de grupo de recebimento de chamadas e, em seguida, atribuindo aos usuários chamadas para grupos de retirada e habilitando os usuários para a retirada de chamadas em grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes com suporte para retirada de chamadas em grupo

Qualquer um dos seguintes clientes pode ser usado para atender chamadas para membros de recebimento de chamadas em grupo:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Os usuários podem usar qualquer um desses clientes para atender chamadas para membros de retirada de chamadas em grupo, mas os usuários devem ser hospedados em um pool do Skype for Business Server ou em um pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de fevereiro. 
  
Os seguintes clientes e dispositivos não têm suporte para selecionar chamadas para membros de retirada de chamadas em grupo:
  
- Lync Mobile
    
- Aplicativo do Lync para Windows 8 e Windows RT
    
- Lync para iPad
    
- Telefones analógicos
    
- Telefones com números de PSTN (Rede Telefônica Pública Comutada)
    
## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário de retirada de chamada de grupo que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas. Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de Call Park, incluindo o recebimento de chamadas em grupo, em ambos os pools. 
  
**Modelo de usuário de retirada de chamadas em grupo**

|**Indicador**|**Por pool <br/> de front-end (com 8 servidores front end)**|**Por servidor padrão da edição**|
|:-----|:-----|:-----|
|Número recomendado de usuários por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuários por pool ativado para Recebimento de chamada de grupo  <br/> |25.000  <br/> |3.000  <br/> |
|Taxa máxima de chamadas recebidas para o total de usuários habilitados para Recebimento de chamada de grupo por pool por minuto  <br/> |500  <br/> |60  <br/> |
|Taxa máxima de chamadas recuperadas por usuários com Recebimento de chamada de grupo por pool por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para pools front-ends com menos de oito servidores front-end, calcule as métricas linearmente. Por exemplo, se o seu pool de front-ends tiver um servidor front-end, calcule a carga máxima como 1/8 dos valores mostrados na tabela. 
  
> [!NOTE]
> Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos desde que você não exceda o número máximo de usuários por pool. Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o recebimento de chamadas em grupo ainda está dentro do modelo de usuário máximo (ou seja, o 120 grupos em que 25 usuários tem 3.000 usuários habilitados para o recebimento de chamadas em grupo). 
  

