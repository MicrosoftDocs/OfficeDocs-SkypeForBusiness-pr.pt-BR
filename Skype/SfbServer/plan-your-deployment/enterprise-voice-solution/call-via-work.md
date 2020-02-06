---
title: Planejar a chamada por meio do trabalho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planejando a chamada por meio do trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e o sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar os telefones PBX.
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803151"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planejar a chamada por meio do trabalho no Skype for Business Server
 
Planejando a chamada por meio do trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e o sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar os telefones PBX.
  
 **Ligar via trabalho** é um novo recurso no Skype for Business Server que permite que você integre a solução Skype for Business aos seus sistemas telefônicos PBX existentes. Um usuário habilitado para chamada por meio de trabalho pode clicar no Skype for Business para fazer chamadas para outro usuário, seja em sua implantação ou em um usuário externo. The call is completed using the user's PBX phone. Isso permite que um usuário com um telefone PBX inclua áudio nas suas conversas avançadas do Skype for Business. Em versões anteriores do controle de chamada remota do Lync Server era um recurso que permitia aos usuários controlar os telefones PBX com o Lync Server. No Skype for Business Server, este recurso foi substituído por meio da chamada por meio do trabalho.
  
Ligar por meio do trabalho permite o seguinte para os usuários de telefones PBX
  
- Experiência Clicar para Chamar, com o áudio fornecido pelo telefone PBX.
    
- Presença, pesquisa de usuário e integração de mensagem instantânea--por exemplo, duas chamadas por usuários de trabalho em uma sessão de mensagem instantânea podem adicionar áudio à sessão, com o áudio fornecido pelos telefones PBX.
    
- A capacidade de adicionar mensagens instantâneas, compartilhamento de aplicativos e transferência de arquivos a uma chamada por meio de uma chamada de trabalho.
    
- Capacidade de ingressar em reuniões com um clique.
    
## <a name="how-it-works"></a>Como funciona

A chamada via trabalho usa a API da Web de comunicação unificada (UCWA) como o agente de usuário back-to-back (B2BUA) entre o sistema PBX e a implantação do Skype for Business Server, para que não seja necessário um gateway CSTA (sistema de telecomunicações compatível com o computador) para se conectar Skype for Business Server com o seu sistema PBX. O UCWA é um serviço apresentado nas versões anteriores do Lync Server para permitir a conectividade com clientes móveis e Web, e é instalado automaticamente em cada servidor front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Fluxo de trabalho de chamadas para uma chamada via chamada de trabalho

Veja a seguir como um usuário habilitado para a chamada via trabalho pode usar o Skype for Business Server para fazer uma chamada:
  
![Mostra as etapas durante uma chamada Telefonar via Trabalho; primeiro o chamador clica para ligar para alguém no cliente Skype for Business; depois o UCWA liga para o telefone do chamador. Quando o chamador atende, o destinatário é chamado](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. O usuário seleciona um usuário em seu cliente Skype for Business e clica no ícone de telefone para chamá-lo. Ou, durante uma conversa de IM, o usuário clica para ligar para o usuário com quem está conversando.
    
2. O telefone PBX do usuário que fez a chamada começa a tocar. A identificação de chamadas para este telefone mostra um número de telefone global que você configurou para ser mostrado na identificação de chamadas de todos os usuários que estão fazendo chamadas por meio de chamadas de trabalho. Esse número de telefone global não é um número de telefone real que corresponde ao telefone de alguém. Trata-se de um sinal visual para informar ao usuário que esta é sua própria chamada de saída, e não uma chamada de entrada que está acontecendo ao mesmo tempo. Ao implantar a chamada pelo trabalho, você deve educar esses usuários sobre esse número de telefone global e o que isso significa.
    
3. O usuário que fez a chamada atende o telefone PBX. Em seguida, o Skype for Business inicia a chamada de voz para o chamador. 
    
4. Quando o destinatário da chamada atende, a chamada de voz começa. Se os dois usuários já têm uma sessão de IM em andamento, ela pode continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Ingressando em uma conferência com Telefonar via Trabalho

Uma chamada por meio de um usuário de trabalho pode ingressar em uma reunião agendada clicando na URL da reunião. O Skype for Business mostra uma mensagem de **discagem para** que o serviço de reunião disque para o telefone PBX do usuário. A chamada via usuário de trabalho então escolhe o telefone PBX e une a reunião.
  
Uma chamada pelo usuário do trabalho também pode usar a opção **reunir agora** no Skype for Business para criar reuniões agora. Então, o usuário vê a mensagem **Discando para** e o telefone PBX toca.
  
Uma chamada por meio de um usuário do trabalho também pode discar para uma reunião chamando o número da ponte de conferência no Skype for Business. Se for necessário um PIN de conferência, o usuário deverá usar o telefone PBX para inserir o PIN.
  
### <a name="incoming-calls"></a>Chamadas de entrada

Quando um usuário habilitado para a chamada por meio do trabalho recebe uma chamada do Skype for Business, o telefone PBX e os clientes do Skype for Business do usuário tocam-se simultaneamente (se o usuário configurou o toque simultâneo). O usuário pode aceitar a chamada ao pegar o telefone PBX ou clicar em **aceitar** na notificação do Skype for Business. Se o usuário aceitar a chamada usando o Skype for Business, a janela do Skype for Business para a chamada permanecerá aberta. Mas se o usuário aceitar a chamada ao pegar o telefone PBX, a janela de notificação do Skype for Business será fechada e não haverá nenhuma sessão do Skype for Business, apenas a chamada de voz pelo telefone PBX.
  
Quando um usuário habilitado para a chamada via trabalho recebe uma chamada PBX, somente o telefone PBX toca.
  
## <a name="limitations-of-call-via-work"></a>Limitações de chamada por meio de trabalho

A chamada via trabalho é uma solução de voz que requer pouca configuração de hardware, mas tem limitações em comparação com os recursos disponíveis em controle de chamada remota ou voz de toda a empresa. A chamada via trabalho tem as seguintes limitações:
  
- Se uma chamada por meio do usuário do trabalho tiver configurado o encaminhamento de chamadas para a chamada via número de retorno de chamada do trabalho e alguém tentar convidar este usuário para uma reunião pelo número de telefone do usuário, o convite não vai alcançar o usuário. Você deve instruir os usuários a convidar participantes para reuniões clicando no nome deles e não no número de telefone. 
    
- O recurso 911 aprimorado e o rastreamento de chamadas maliciosas não estão disponíveis durante chamadas por meio de chamadas de trabalho.
    
- Os usuários habilitados para chamada via trabalho não podem usar os recursos de delegação, chamada de equipe ou grupo de resposta.
    
- Os usuários da chamada via trabalho não podem usar o Skype for Business para gravar uma reunião, ativar ou desativar o mudo da chamada, reter ou transferir a chamada ou usar o estacionamento de chamadas.
    
- Os usuários não podem usar a chamada por meio do trabalho para acessar suas mensagens de correio de voz PBX.
    
- Os usuários da chamada via trabalho não podem escalonar uma sessão que é iniciada como uma chamada de voz para uma reunião colaborativa que inclui comunicações como vídeo, PowerPoint, quadro de comunicações ou uma anotação.
    
- Os usuários da chamada via trabalho não podem adicionar mais usuários a uma chamada de duas pessoas.
    
- Não há suporte para o emparelhamento de telefones fixos ou de plug-in VDI.
    
- Se um usuário fizer ou responder uma chamada usando o telefone PBX (e não estiver usando a janela do Skype for Business), não haverá o registro da chamada.
    
- Se o seu sistema PBX não oferecer suporte a **referir-se a substituições**, o seguinte comportamento ocorrerá. Durante uma chamada via chamada de trabalho, se o usuário transferir a chamada em andamento do telefone PBX, a janela de chamada não desaparecerá da janela do Skype for Business. Se o usuário fechar a janela de chamada, a chamada entre o destino de transferência e o transferido será encerrada. 
    
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para ligar pelo trabalho

Para habilitar qualquer usuário para chamada por meio do trabalho, você deve ter alguns pré-requisitos no lugar. Para obter mais informações sobre esses pré-requisitos e sobre as etapas sobre como permitir que os usuários liguem por meio do trabalho, consulte [implantar chamada via trabalho no Skype for Business Server 2015](../../deploy/deploy-call-via-work.md). 
  
## <a name="see-also"></a>Confira também

[Plano de controle de chamada remota no Skype for Business](remote-call-control.md)
  
[Implantar Telefonar via Trabalho no Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

