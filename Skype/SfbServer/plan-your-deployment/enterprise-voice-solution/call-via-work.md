---
title: Planejar para chamada Via trabalho no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planejamento de chamada Via trabalho no Skype para Business Server, que permite integração entre o Skype para a empresa e seu sistema telefônico PBX, para que os usuários podem utilizar Skype for Business para controlar seus telefones PBX.
ms.openlocfilehash: 3a2452f732d55f305d91cee9cd2b940f7bb3c88e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207241"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planejar para chamada Via trabalho no Skype para Business Server
 
Planejamento de chamada Via trabalho no Skype para Business Server, que permite integração entre o Skype para a empresa e seu sistema telefônico PBX, para que os usuários podem utilizar Skype for Business para controlar seus telefones PBX.
  
 **Chamada Via trabalho** é um novo recurso do Skype para Business Server, que permite que você integre sua Skype para solução de negócios com seus sistemas de telefone PBX existentes. Um usuário habilitado para chamada Via trabalho pode clicar em Skype para a chamada a outro usuário, tanto dentro de sua implantação ou um usuário externo de negócios. The call is completed using the user's PBX phone. Isso permite que um usuário com um telefone PBX incluir áudio em seu rich Skype para conversas de negócios. Nas versões anteriores de chamada remota do Lync Server controle era um recurso que permitia aos usuários controlar seus telefones PBX com o Lync Server. Skype para Business Server, esse recurso foi substituído com a chamada Via trabalho.
  
Chamada Via trabalho permite que o seguinte para usuários de telefone PBX
  
- Experiência Clicar para Chamar, com o áudio fornecido pelo telefone PBX.
    
- Presença, pesquisa de usuário e integração de mensagens Instantâneas – por exemplo, dois usuários de chamada Via trabalho em uma sessão de mensagens Instantâneas podem adicionar áudio à sua sessão, com o áudio fornecido em telefones PBX.
    
- A capacidade de adicionar mensagens Instantâneas, compartilhamento de aplicativos e transferência de arquivos a uma chamada de chamada Via trabalho.
    
- Capacidade de ingressar em reuniões com um clique.
    
## <a name="how-it-works"></a>Como funciona

Chamada Via trabalho usa Unified Communications Web API (UCWA) como o agente do usuário em frente e verso (B2BUA) entre o sistema PBX e sua Skype para implantação de servidor de negócios, de modo que nenhum gateway (CSTA) do aplicativo de telecomunicações suportado por computador é necessário para conectar Skype para Business Server com seu sistema PBX. UCWA é um serviço introduzido em versões anteriores do Microsoft Lync Server para habilitar a conectividade com o mobile e clientes web e é instalado automaticamente em cada servidor Front-End.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Chamar o fluxo de trabalho para uma chamada de chamada Via trabalho

O exemplo a seguir ilustra como um usuário habilitado para chamada Via trabalho pode usar o Skype para Business Server para fazer uma chamada:
  
![Mostra as etapas durante uma chamada Telefonar via Trabalho; primeiro o chamador clica para ligar para alguém no cliente Skype for Business; depois o UCWA liga para o telefone do chamador. Quando o chamador atende, o destinatário é chamado](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. O usuário seleciona um usuário em seu Skype para o cliente de negócios e clica no ícone de telefone para telefonar para ele. Ou, durante uma conversa de IM, o usuário clica para ligar para o usuário com quem está conversando.
    
2. O telefone PBX do usuário que fez a chamada começa a tocar. A ID do chamador para esse telefone mostra um número de telefone global que você definiu para mostrar a ID do chamador de todos os usuários fazer chamadas de chamada Via trabalho. Esse número de telefone global não é um número de telefone real que corresponde ao telefone de alguém. Trata-se de um sinal visual para informar ao usuário que esta é sua própria chamada de saída, e não uma chamada de entrada que está acontecendo ao mesmo tempo. Quando você implanta chamada Via trabalho, você deve instruir os usuários sobre esse número de telefone global e o que significa.
    
3. O usuário que fez a chamada atende o telefone PBX. Skype para os negócios, em seguida, inicia a chamada de voz para o receptor. 
    
4. Quando o destinatário da chamada atende, a chamada de voz começa. Se os dois usuários já têm uma sessão de IM em andamento, ela pode continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Ingressando em uma conferência com Telefonar via Trabalho

Um usuário de chamada Via trabalho pode ingressar em uma reunião agendada, clicando na URL de reunião. Skype para negócios mostra uma mensagem de **discagem para** até que o serviço de reunião disca o telefone PBX do usuário. O usuário de chamada Via trabalho tira o telefone PBX e participa da reunião.
  
Um usuário de chamada Via trabalho também pode usar a opção **Reunir agora** no Skype for Business para criar reuniões reunir agora. Então, o usuário vê a mensagem **Discando para** e o telefone PBX toca.
  
Um usuário de chamada Via trabalho também pode discar para uma reunião chamando-se o número de ponte de conferência de dentro do Skype para negócios. Se for necessário um PIN de conferência, o usuário deverá usar o telefone PBX para inserir o PIN.
  
### <a name="incoming-calls"></a>Chamadas de entrada

Quando um usuário habilitado para chamada Via trabalho recebe um Skype para chamada de negócios, o telefone PBX e Skype do usuário para os clientes corporativos que todos toquem simultaneamente (se o usuário tiver configurado o toque simultâneo). O usuário pode aceitar a chamada por pegando o telefone PBX ou clicar em **Aceitar** no Skype para fins de notificação de negócios. Se o usuário aceitar a chamada usando o Skype para a empresa, o Skype para a janela de negócios para a chamada permanece aberta. Mas, se o usuário aceitar a chamada pegando o telefone PBX, em seguida, fecha o Skype para a janela de notificação de negócios e não há nenhuma Skype para sessão de negócios, apenas a chamada de voz no telefone PBX.
  
Quando um usuário habilitado para chamada Via trabalho recebe uma chamada de PBX, somente o telefone tocar de PBX.
  
## <a name="limitations-of-call-via-work"></a>Limitações da chamada Via trabalho

Chamada Via trabalho é uma solução de voz que requer pouca configuração de hardware, mas tem limitações em comparação com os recursos disponíveis no completo Enterprise Voice ou controle de chamada remota. Chamada Via trabalho tem as seguintes limitações:
  
- Se um usuário de chamada Via trabalho configurou o encaminhamento de chamadas para o número de retorno de chamada Via trabalho e alguém tentar convidar o usuário para uma reunião por número de telefone do usuário, o convite não atinja o usuário. Você deve instruir os usuários a convidar participantes para reuniões clicando no nome deles e não no número de telefone. 
    
- Capacidade aprimorada de 911 e rastreamento de chamadas maliciosas não estão disponíveis durante as chamadas de chamada Via trabalho.
    
- Os usuários habilitados para chamada Via trabalho não é possível usar a delegação, chamada de equipe ou recursos do grupo de resposta.
    
- Usuários de chamada Via trabalho não podem usar Skype for Business para gravar uma reunião, ativar mudo ou desativar o mudo a chamada, mantenha ou transferir a chamada ou use o estacionamento de chamadas.
    
- Os usuários não é possível usar a chamada Via trabalho para acessar suas mensagens de caixa postal do PBX.
    
- Usuários de chamada Via trabalho não podem escalonar uma sessão iniciados como uma chamada de voz para uma reunião colaborativa que inclui as comunicações, como vídeo, Powerpoint, quadro de comunicações ou uma observação.
    
- Usuários de chamada Via trabalho não é possível adicionar mais usuários a uma chamada de pessoa-2.
    
- Não há suporte para o emparelhamento de telefones fixos ou de plug-in VDI.
    
- Se um usuário faz ou atende uma chamada usando o telefone PBX (e não usando o Skype para a janela de negócios), não haverá nenhum log da chamada.
    
- Se o seu sistema PBX não oferece suporte a **referência com substitui**, acontecerá o seguinte comportamento. Enquanto estiver em uma chamada de chamada Via trabalho, se o usuário transfere a chamada em andamento do telefone PBX, a janela de chamada não desaparecerão de seu Skype para a janela de negócios. Se o usuário, em seguida, fecha a janela de chamada, a chamada entre o destino de transferência e o destinatário será finalizado. 
    
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para chamada Via trabalho

Para habilitar os usuários para chamada Via trabalho, você deve ter alguns programas de pré-requisito no lugar. Para obter mais informações sobre esses pré-requisitos e para obter etapas sobre como habilitar usuários para chamada Via trabalho, consulte [Implantar chamada Via trabalho no Skype para Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Confira também

[Planejar o controle de chamada remota no Skype para negócios](remote-call-control.md)
  
[Implantar Telefonar via Trabalho no Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

