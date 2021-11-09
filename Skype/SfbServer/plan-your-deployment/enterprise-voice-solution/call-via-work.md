---
title: Planejar a chamada via trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planejando a chamada via trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e seu sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar seus telefones PBX.
ms.openlocfilehash: 0dddb601ecf9928aa1bd1cd63bc8ed3628a1330d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854215"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planejar a chamada via trabalho no Skype for Business Server
 
Planejando a chamada via trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e seu sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar seus telefones PBX.
  
 **Call Via Work é** um novo recurso no Skype for Business Server que permite integrar sua solução Skype for Business com seus sistemas de telefone PBX existentes. Um usuário habilitado para o Call Via Work pode clicar em Skype for Business para chamar outro usuário, dentro da sua implantação ou de um usuário externo. A chamada é concluída usando o telefone PBX do usuário. Isso permite que um usuário com um telefone PBX inclua áudio em suas conversas Skype for Business rich. Em versões anteriores do controle de chamada remota do Lync Server, era um recurso que permitia aos usuários controlar seus telefones PBX com o Lync Server. Em Skype for Business Server, esse recurso foi substituído por Call Via Work.
  
Chamada via trabalho habilita o seguinte para usuários de telefone PBX
  
- Experiência de clique para chamada, com o áudio fornecido por meio do telefone PBX.
    
- Presença, pesquisa de usuário e integração com mensagens de usuário, por exemplo, dois usuários de Chamada Via Trabalho em uma sessão de mensagens de IM podem adicionar áudio à sessão, com o áudio fornecido por meio dos telefones PBX.
    
- A capacidade de adicionar mensagens de IM, compartilhamento de aplicativos e transferência de arquivo a uma chamada via trabalho.
    
- Recurso de junção de reunião com um clique
    
## <a name="how-it-works"></a>Como funciona

A Call Via Work usa a UCWA (Unified Communications Web API) como o agente de usuário de back-to-back (B2BUA) entre o sistema PBX e sua implantação Skype for Business Server, para que nenhum gateway CSTA (aplicativo de telecomunicações) com suporte no computador seja necessário para se conectar ao Skype for Business Server com seu sistema PBX. O UCWA é um serviço introduzido nas versões anteriores do Lync Server para habilitar a conectividade com clientes móveis e web e é instalado automaticamente em todos os Servidores Front-End.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Fluxo de trabalho de chamada para uma chamada via trabalho

O seguinte ilustra como um usuário habilitado para o Call Via Work pode usar o Skype for Business Server para fazer uma chamada:
  
![Mostra as etapas durante uma chamada via trabalho; primeiro, o chamador clica para chamar alguém no Skype for Business cliente; em seguida, o UCWA toca o telefone do chamador. Quando o chamador atende o telefone, o destinatário é chamado.](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. O usuário seleciona um usuário em seu Skype for Business cliente e clica no ícone do telefone para chamá-lo. Ou, durante uma conversa de IM, o usuário clica para chamar o usuário com o que está tendo a sessão.
    
2. O telefone PBX do usuário que fez a chamada começa a tocar. A ID do chamador deste telefone mostra um número de telefone global que você definiu para mostrar a ID do chamador de todos os usuários que estão colocando chamadas via trabalho. Esse número de telefone global não é um número de telefone real que corresponde ao telefone de uma pessoa. Em vez disso, é um sinal visual para que um usuário saiba que essa é sua própria chamada de saída, e não uma chamada de entrada acontecendo ao mesmo tempo. Ao implantar a Chamada Via Trabalho, você deve instruir esses usuários sobre esse número de telefone global e o que ele significa.
    
3. O usuário que fez a chamada atende o telefone PBX. Skype for Business inicia a chamada de voz para o chamador. 
    
4. Quando o chamador responde, a chamada de voz é iniciada. Se os dois usuários já tinham uma sessão de IM em uso, ela pode continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Ingressar em uma conferência com chamada via trabalho

Um usuário de Chamada Via Trabalho pode ingressar em uma reunião agendada clicando na URL da reunião. Skype for Business mostra uma **discagem** para mensagem até que o serviço de reunião disce o telefone PBX do usuário. O usuário de Chamada Via Trabalho, em seguida, pega o telefone PBX e inssive na reunião.
  
Um usuário de Chamada Via Trabalho também pode usar a **opção Reunir Agora** Skype for Business criar reuniões do Meet Now. Em seguida, o usuário vê **a discagem para a** mensagem e o telefone PBX toca.
  
Um usuário de Chamada Via Trabalho também pode discar para uma reunião chamando o número da Ponte de Conferência de dentro Skype for Business. Se um PIN de conferência for necessário, o usuário deverá usar seu telefone PBX para inserir o PIN.
  
### <a name="incoming-calls"></a>Chamadas de entrada

Quando um usuário habilitado para o Call Via Work recebe uma chamada Skype for Business, o telefone PBX e os clientes Skype for Business do usuário tocarão simultaneamente (se o usuário tiver definido o toque simultâneo). O usuário pode aceitar a chamada atendendo o telefone PBX ou clicando em **Aceitar** na notificação Skype for Business. Se o usuário aceitar a chamada usando Skype for Business, a janela Skype for Business da chamada permanecerá aberta. Mas se o usuário aceitar a chamada atendendo o telefone PBX, Skype for Business janela de notificação será fechada e não haverá nenhuma sessão Skype for Business, somente a chamada de voz pelo telefone PBX.
  
Quando um usuário habilitado para Chamadas Via Trabalho recebe uma chamada PBX, apenas o telefone PBX toca.
  
## <a name="limitations-of-call-via-work"></a>Limitações da chamada via trabalho

Call Via Work é uma solução de voz que requer pouca configuração de hardware, mas tem limitações em comparação com os recursos disponíveis em controle Enterprise Voice ou de chamada remota. A chamada via trabalho tem as seguintes limitações:
  
- Se um usuário de Chamada Via Trabalho tiver definido o encaminhamento de chamada para o número de retorno de chamada Via Trabalho e alguém tentar convidar esse usuário para uma reunião pelo número de telefone do usuário, o convite não alcançará o usuário. Você deve instruir seus usuários a convidar participantes para reuniões clicando no nome, não no número de telefone. 
    
- Recursos aprimorados do 911 e rastreamento de chamadas mal-intencionadas não estão disponíveis durante chamadas via trabalho.
    
- Os usuários habilitados para Call Via Work não podem usar os recursos de delegação, chamada de equipe ou grupo de resposta.
    
- Os usuários do Call Via Work não podem Skype for Business para gravar uma reunião, silenciar ou desativar a chamada, segurar ou transferir a chamada ou usar o estacionamento de chamada.
    
- Os usuários não podem usar Call Via Work para acessar suas mensagens de caixa postal PBX.
    
- Os usuários do Call Via Work não podem escalonar uma sessão que começou como uma chamada de voz para uma reunião colaborativa que inclui comunicações como vídeo, Powerpoint, quadro de comunicações ou One Note.
    
- Os usuários do Call Via Work não podem adicionar mais usuários a uma chamada de duas pessoas.
    
- Não há suporte para emparelhamento de telefone de mesa ou emparelhamento de plug-in VDI.
    
- Se um usuário fizer ou atender a uma chamada usando o telefone PBX (e não estiver usando a janela de Skype for Business), não haverá log da chamada.
    
- Se o sistema PBX não tiver suporte **para REFER com Substituições,** o comportamento a seguir ocorrerá. Em uma chamada chamada via trabalho, se o usuário transferir a chamada em andamento do pbx Telefone, a janela de chamada não desaparecerá de sua janela Skype for Business. Se o usuário fechar a janela de chamada, a chamada entre o destino de transferência e o transferidor terminará. 
    
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para chamada via trabalho

Para habilitar qualquer usuário para Call Via Work, você deve ter alguns pré-requisitos no local. Para obter mais informações sobre esses pré-requisitos e para obter etapas sobre como habilitar usuários para o Call Via Work, consulte [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Confira também

[Planejar o controle de chamada remota no Skype for Business](remote-call-control.md)
  
[Implantar chamada via trabalho no Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

