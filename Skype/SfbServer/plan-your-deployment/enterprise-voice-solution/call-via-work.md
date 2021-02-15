---
title: Planejar o Telefonar via Trabalho no Skype for Business Server
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: Planejamento do Telefonar via Trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e seu sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar seus telefones PBX.
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825871"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a>Planejar o Telefonar via Trabalho no Skype for Business Server
 
Planejamento do Telefonar via Trabalho no Skype for Business Server, que permite a integração entre o Skype for Business e seu sistema de telefonia PBX, para que os usuários possam usar o Skype for Business para controlar seus telefones PBX.
  
 **Telefonar via Trabalho** é um novo recurso no Skype for Business Server que permite integrar sua solução do Skype for Business com seus sistemas de telefone PBX existentes. Um usuário habilitado para Telefonar via Trabalho pode clicar no Skype for Business para ligar para outro usuário, dentro de sua implantação ou em um usuário externo. A chamada é concluída usando o telefone PBX do usuário. Isso permite que um usuário com um telefone PBX inclua áudio em suas conversas rica do Skype for Business. Em versões anteriores do controle de chamada remota do Lync Server, era um recurso que permitia que os usuários controlas seus telefones PBX com o Lync Server. No Skype for Business Server, esse recurso foi substituído pelo Telefonar via Trabalho.
  
Telefonar via Trabalho habilita o seguinte para usuários de telefone PBX
  
- Experiência clique para chamar, com o áudio fornecido por meio do telefone PBX.
    
- Presença, pesquisa de usuário e integração de mensagens im — por exemplo, dois usuários de Telefonar via Trabalho em uma sessão de IM podem adicionar áudio à sessão, com o áudio fornecido por meio dos telefones PBX.
    
- A capacidade de adicionar mensagens im, compartilhamento de aplicativos e transferência de arquivos a uma chamada Telefonar via Trabalho.
    
- Recurso de ingressar em reunião com um clique
    
## <a name="how-it-works"></a>Como funciona

O Call Via Work usa a Unified Communications Web API (UCWA) como o agente de usuário back-to-back (B2BUA) entre o sistema PBX e sua implantação do Skype for Business Server, para que nenhum gateway CSTA (aplicativo de telecomunicações) com suporte no computador seja necessário para conectar o Skype for Business Server ao seu sistema PBX. O UCWA é um serviço introduzido em versões anteriores do Lync Server para habilitar a conectividade com clientes móveis e da Web e é instalado automaticamente em cada Servidor front-end.
  
### <a name="call-workflow-for-a-call-via-work-call"></a>Fluxo de trabalho de chamada para uma chamada Telefonar via Trabalho

O exemplo a seguir ilustra como um usuário habilitado para Telefonar via Trabalho pode usar o Skype for Business Server para fazer uma chamada:
  
![Mostra as etapas durante uma chamada Telefonar via Trabalho; primeiro o chamador clica para ligar para alguém no cliente Skype for Business; em seguida, o UCWA toca no telefone do chamador. Quando o chamador atende o telefone, o destinatário é chamado](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. O usuário seleciona um usuário no cliente skype for business e clica no ícone de telefone para chamá-lo. Ou, durante uma conversa de IM, o usuário clica para ligar para o usuário com quem está tendo a sessão.
    
2. O telefone PBX do usuário que fez a chamada começa a tocar. A ID de chamadas deste telefone mostra um número de telefone global que você definiu para mostrar na ID de chamadas de todos os usuários fazendo chamadas Telefonar via Trabalho. Esse número de telefone global não é um número de telefone real que corresponde ao telefone de uma pessoa. Em vez disso, é um sinal visual para permitir que um usuário saiba que esta é sua própria chamada de saída, e não uma chamada de entrada que está acontecendo ao mesmo tempo. Ao implantar o Telefonar via Trabalho, você deve instruir esses usuários sobre esse número de telefone global e o que isso significa.
    
3. O usuário que fez a chamada atende o telefone PBX. Em seguida, o Skype for Business inicia a chamada de voz para o destinatário da chamada. 
    
4. Quando o destinatário da chamada atender, a chamada de voz começará. Se os dois usuários já tinham uma sessão de IM em operação, ela pode continuar.
    
### <a name="joining-a-conference-with-call-via-work"></a>Ingressar em uma conferência com Telefonar via Trabalho

Um usuário de Telefonar via Trabalho pode ingressar em uma reunião agendada clicando na URL da reunião. Em seguida, o Skype for Business mostra **uma discagem para** mensagem até que o serviço de reunião disque para o telefone PBX do usuário. Em seguida, o usuário telefonar via trabalho atende o telefone PBX e participa da reunião.
  
Um usuário de Telefonar via Trabalho também pode usar a **opção Reunir Agora** no Skype for Business para criar reuniões Reunir Agora. Em seguida, o usuário vê **a discagem para a** mensagem e o telefone PBX toca.
  
Um usuário de Telefonar via Trabalho também pode discar para uma reunião ligando para o número da ponte de conferência de dentro do Skype for Business. Se for necessário um PIN de conferência, o usuário deverá usar seu telefone PBX para inserir o PIN.
  
### <a name="incoming-calls"></a>Chamadas de entrada

Quando um usuário habilitado para Telefonar via Trabalho recebe uma chamada do Skype for Business, o telefone PBX e os clientes do Skype for Business do usuário toam simultaneamente (se o usuário tiver definido o toque simultâneo). O usuário pode aceitar a chamada atendendo o telefone PBX ou clicando em **Aceitar** na notificação do Skype for Business. Se o usuário aceitar a chamada usando o Skype for Business, a janela do Skype for Business para a chamada permanecerá aberta. Mas se o usuário aceitar a chamada atendendo o telefone PBX, a janela de notificação do Skype for Business será fechada e não haverá sessão do Skype for Business, somente a chamada de voz pelo telefone PBX.
  
Quando um usuário habilitado para Telefonar via Trabalho recebe uma chamada PBX, somente o telefone PBX toca.
  
## <a name="limitations-of-call-via-work"></a>Limitações do Telefonar via Trabalho

Telefonar via Trabalho é uma solução de voz que requer pouca configuração de hardware, mas tem limitações em comparação com os recursos disponíveis no Enterprise Voice completo ou no controle de chamada remota. O Telefonar via Trabalho tem as seguintes limitações:
  
- Se um usuário de Telefonar via Trabalho tiver definido o encaminhamento de chamadas para o número de retorno de chamada Telefonar via Trabalho e alguém tentar convidar esse usuário para uma reunião pelo número de telefone do usuário, o convite não chegará ao usuário. Você deve instruir os usuários a convidar participantes para reuniões clicando no nome, não no número de telefone. 
    
- A funcionalidade 911 aprimorada e o rastreamento de chamadas mal-intencionadas não estão disponíveis durante chamadas Telefonar via Trabalho.
    
- Os usuários habilitados para Telefonar via Trabalho não podem usar os recursos de delegação, chamada de equipe ou grupo de resposta.
    
- Os usuários do Telefonar via Trabalho não podem usar o Skype for Business para gravar uma reunião, silenciar ou desativar o mudo da chamada, manter ou transferir a chamada ou usar o estacionamento de chamada.
    
- Os usuários não podem usar Telefonar via Trabalho para acessar suas mensagens de caixa postal PBX.
    
- Os usuários do Telefonar via Trabalho não podem escalonar uma sessão que começou como uma chamada de voz para uma reunião colaborativa que inclui comunicações como vídeo, Powerpoint, quadro de comunicações ou One Note.
    
- Os usuários do Telefonar via Trabalho não podem adicionar mais usuários a uma chamada de duas pessoas.
    
- Não há suporte para emparelhamento de telefone de mesa ou emparelhamento de plug-in VDI.
    
- Se um usuário fizer ou atender uma chamada usando o telefone PBX (e não estiver usando a janela do Skype for Business), não haverá log da chamada.
    
- Se seu sistema PBX não tiver suporte para **REFER com substituições,** o comportamento a seguir ocorrerá. Enquanto estiver em uma chamada Telefonar via Trabalho, se o usuário transferir a chamada em andamento do Telefone PBX, a janela de chamada não desaparecerá da janela do Skype for Business. Se o usuário fechar a janela de chamada, a chamada entre o destino da transferência e o destinatário será finalada. 
    
## <a name="prerequisites-for-call-via-work"></a>Pré-requisitos para Telefonar via Trabalho

Para habilitar qualquer usuário para Telefonar via Trabalho, você deve ter alguns pré-requisitos. Para obter mais informações sobre esses pré-requisitos e para obter etapas sobre como habilitar usuários para Telefonar via Trabalho, consulte [Deploy Call Via Work in Skype for Business Server 2015.](../../deploy/deploy-call-via-work.md) 
  
## <a name="see-also"></a>Confira também

[Planejar o controle de chamada remota no Skype for Business](remote-call-control.md)
  
[Implantar Telefonar via Trabalho no Skype for Business Server 2015](../../deploy/deploy-call-via-work.md)

