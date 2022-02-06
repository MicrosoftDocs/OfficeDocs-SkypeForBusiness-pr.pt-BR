---
title: Planejar a coleta de chamada de grupo no Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 'Planejando a Coleta de Chamadas de Grupo Skype for Business Server Enterprise Voice, o que permite que os usuários atendam chamadas originalmente destinadas a outras pessoas.'
---

# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planejar a coleta de chamada de grupo no Skype for Business
 
Planejando a Coleta de Chamadas de Grupo Skype for Business Server Enterprise Voice, o que permite que os usuários atendam chamadas originalmente destinadas a outras pessoas.
  
O Recebimento de Chamadas de Grupo permite que os usuários atendam a chamadas de entrada para seus colegas de seus próprios telefones. Isso aumenta a disponibilidade da linha de um usuário, permitindo que outros usuários atendam a uma chamada de entrada discando um número de grupo de recebimento de chamadas. Quando o Recebimento de Chamadas de Grupo é implantado, o número de chamadas de entrada roteadas para a caixa postal pode ser significativamente reduzido, o que é particularmente útil para chamadas de clientes externos à sua organização.
  
O recurso de Retirada de Chamada de Grupo foi projetado especialmente para unidades de negócios em ambientes de escritório aberto. As chamadas de entrada não são disruptivas porque elas toam apenas no destino pretendido. Outros usuários que ouvem o toque, no entanto, ainda podem atender a chamada simplesmente discando o número do grupo. 
  
Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum são geograficamente distribuídos, a chamada de equipe apresenta a solução mais adequada. A principal diferença entre o Recebimento de Chamadas de Grupo e a chamada de equipe é que, com o Recebimento de Chamadas de Grupo, uma chamada de entrada toca apenas no destino pretendido, mas qualquer pessoa ainda pode optar por respondê-la discando um número de grupo. Com a chamada de equipe, a chamada toca em todos os telefones dos membros da equipe, e qualquer usuário na equipe pode pegar o telefone para atender a chamada. Uma diferença adicional entre o Atendimento de Chamada de Grupo e a chamada de equipe é que a Coleta de Chamada de Grupo é gerenciada por um administrador, por meio Skype for Business Server. Com a chamada de equipe, os usuários finais gerenciam o recurso usando o Skype for Business cliente. Com a Coleta de Chamada de Grupo, portanto, esse aspecto do gerenciamento de chamada pode ser centralizado.
  
A Coleta de Chamada de Grupo é criada no aplicativo Estacionamento de Chamada. Ao implantar a Coleta de Chamada de Grupo, você configura a tabela de órbita do estacionamento de chamada com intervalos separados de números de extensão designados como números de grupo de retirada de chamada. Assim como os números de órbita do estacionamento de chamada, os números do grupo de retirada de chamadas devem ser extensões virtuais que não tenham nenhum usuário ou telefone atribuído a eles. Cada pool de Front-End onde você implanta a Coleta de Chamada de Grupo pode ter um ou mais intervalos de números de grupo de retirada de chamada. Os intervalos de número de grupo devem ser globalmente exclusivos na implantação Skype for Business Server grupo. 
  
> [!NOTE]
> Os intervalos de números designados como números de Retirada de Chamada de Grupo na tabela de órbita do estacionamento de chamada não podem ser gerenciados ou exibidos usando o Painel de Controle Skype for Business Server Grupo. A única maneira de ver todos os intervalos de números na tabela de órbita do estacionamento de chamada é usar Skype for Business Server Shell de Gerenciamento. Da mesma forma, a única maneira de adicionar, modificar ou remover números de Retirada de Chamada de Grupo é usar Skype for Business Server Shell de Gerenciamento. 
  
Depois de configurar os números do grupo de retirada de chamada, atribua usuários a um grupo de retirada de chamada. Qualquer usuário atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada é feita para um usuário atribuído a um grupo de atendimento de chamada, qualquer outro usuário que perceba a chamada pode respondê-la discando manualmente o número do grupo de atendimento de chamada. O usuário que atende a chamada não precisa ser membro do grupo. Quando uma chamada é a escolhida por outro usuário, uma notificação é enviada para o número originalmente chamado.
  
> [!NOTE]
> Um usuário pode ser membro de apenas um grupo de atendimento de chamada. 
  
> [!NOTE]
> Embora qualquer usuário na implantação Skype for Business Server possa atender a uma chamada para um membro do grupo de atendimento de chamada, a pessoa que atende a chamada deve saber o número correto do grupo de retirada de chamada para discar. 
  
Se um usuário discar um número de grupo de atendimento de chamada para atender a uma chamada quando vários telefones no grupo estão tocando, o usuário responde à chamada que está tocando há mais tempo.
  
As configurações de toque simultâneo funcionarão para os usuários que têm o atendimento de chamada de grupo. Ou seja, uma chamada feita a um usuário que tem o Atendimento de Chamada de Grupo tocará para todos os destinos configurados, e outro usuário poderá responder à chamada. A exceção a essa regra é quando o usuário configura toque simultâneo para chamar todos os membros da equipe.
  
O Atendimento de Chamadas de Grupo não pode ser usado para atender aos seguintes tipos de chamadas:
  
- Chamadas para uma linha privada
    
- Chamadas de um contato que recebeu a relação de privacidade Amigos e Família
    
    > [!TIP]
    > Um usuário que é membro de um grupo de retirada de chamadas pode impedir que determinadas chamadas possam ser recuperadas por meio do Atendimento de Chamadas de Grupo marcando o contato como um contato pessoal no cliente Skype for Business de grupo. Para marcar um contato como um contato pessoal, de definir a Relação de Privacidade do contato como Amigos e Família. Qualquer chamada de entrada de contatos com a Relação de Privacidade definida como Amigos e Família não pode ser recuperada usando o Recebimento de Chamadas de Grupo. 
  
- Parte de vídeo de chamadas de áudio/vídeo 
    
    > [!NOTE]
    > Se um usuário responder a uma chamada de áudio/vídeo, o usuário receberá apenas o áudio. A pessoa que está chamando ou a pessoa que atende a chamada pode escalonar a chamada para adicionar vídeo. 
  
- Chamadas de toque simultâneas que são roteados para membros de chamada de equipe
    
- Chamadas roteada para um representante
    
- Chamadas roteada para um grupo de resposta
    
Os seguintes tipos de usuários não podem participar da Coleta de Chamada de Grupo. Ou seja, eles não devem ser incluídos em um grupo de Atendimento de Chamadas de Grupo e não podem atender chamadas para usuários que tenham a Retirada de Chamadas de Grupo habilitada.
  
- Usuários que estão em casa online em uma implantação híbrida
    
- Usuários que não estão em casa em um pool do Skype for Business Server 2015 ou em um pool do Lync Server 2013 com Atualizações Cumulativas para o Lync Server 2013: fevereiro de 2013 em uma implantação local
    
Se ninguém atender a uma chamada para um membro de um grupo de atendimento de chamada, a chamada será roteada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para a caixa postal ou é encaminhada para um destino diferente, conforme especificado nas configurações do cliente.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

A Coleta de Chamada de Grupo é implantada automaticamente quando você implanta Enterprise Voice e o aplicativo Estacionamento de Chamada. Você habilita o Atendimento de Chamada de Grupo configurando a tabela de órbita do Estacionamento de Chamada com intervalos separados de números designados como números de grupo de retirada de chamada e atribuindo usuários a grupos de retirada de chamada e habilitando os usuários para o Atendimento de Chamada de Grupo.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clientes com suporte para Coleta de Chamada de Grupo

Qualquer um dos seguintes clientes pode ser usado para atender chamadas aos membros do Group Call Pickup:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Os usuários podem usar qualquer um desses clientes para atender chamadas aos membros do Group Call Pickup, mas os usuários devem estar em um pool de Skype for Business Server ou em um pool do Lync Server 2013 com Atualizações Cumulativas para o Lync Server 2013: fevereiro de 2013. 
  
Os seguintes clientes e dispositivos não têm suporte para atender chamadas aos membros do Group Call Pickup:
  
- Lync Mobile
    
- Aplicativo do Lync para Windows 8 e Windows RT
    
- Lync para iPad
    
- Telefones analógicos
    
- Telefones com números PSTN (rede telefônica pública comutado)
    
## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário de Retirada de Chamada de Grupo que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> A Retirada de Chamada de Grupo se baseia no aplicativo Estacionamento de Chamada. Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de Estacionamento de Chamada, incluindo a Retirada de Chamada de Grupo, em ambos os pools. 
  
**Modelo de usuário de retirada de chamada de grupo**

|**Indicador**|**Por pool de front-end  <br/>  (com 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Número recomendado de usuários por grupo  <br/> |50  <br/> |50  <br/> |
|Número recomendado de grupos  <br/> |500  <br/> |60  <br/> |
|Número máximo de usuários por pool habilitados para o Atendimento de Chamada de Grupo  <br/> |25.000  <br/> |3,000  <br/> |
|Taxa máxima de chamadas de entrada para o total de usuários habilitados para Recebimento de Chamadas de Grupo por pool por minuto  <br/> |500  <br/> |60  <br/> |
|Taxa máxima de chamadas recuperadas pelos usuários com Coleta de Chamadas de Grupo por pool por minuto  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Para pools de Front-End com menos de oito Servidores Front-End, calcule as métricas linearmente. Por exemplo, se o pool de Front-End tiver um Servidor Front-End, calcule a carga máxima como 1/8 dos valores mostrados na tabela. 
  
> [!NOTE]
> Você pode aumentar ou diminuir o número recomendado de usuários por grupo e o número de grupos, desde que não exceda o número máximo de usuários por pool. Por exemplo, seu servidor Edição Standard pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o Atendimento de Chamada de Grupo ainda está dentro do máximo do modelo de usuário (ou seja, 120 grupos vezes 25 usuários são 3.000 usuários habilitados para o Atendimento de Chamada de Grupo). 
  

