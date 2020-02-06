---
title: Planeje o estacionamento de chamadas no Skype for Business
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejando o estacionamento de chamadas no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas e clientes compatíveis.
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803191"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planeje o estacionamento de chamadas no Skype for Business
 
Planejando o estacionamento de chamadas no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas e clientes compatíveis.
  
O aplicativo de estacionamento de chamadas permite que os usuários do Enterprise Voice façam o seguinte:
  
- Colocar uma chamada em espera e recuperá-la no mesmo telefone ou em outro.
    
- Colocar uma chamada em espera para transferi-la para um departamento ou área geral, por exemplo, um departamento de vendas ou um depósito onde há um telefone de área comum.
    
- Colocar uma chamada em espera e manter o telefone original livre para outras chamadas.
    
Quando um usuário representa uma chamada, o Skype for Business Server transfere a chamada para um número temporário, chamado de órbita, onde a chamada é mantida até ser recuperada ou expirada. O Skype for Business Server envia a órbita ao usuário que estaciona a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no link de órbita ou na janela de Conversação. 
  
O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas ou um sistema de paginação, para comunicar o número de órbita para outra pessoa. O usuário que estacionou a chamada pode deixar a janela de Conversação aberta para receber notificações quando a chamada for recuperada.
  
Como intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Skype for Business ou de um telefone PBX se o roteamento estiver configurado corretamente. Se ninguém recuperar a chamada dentro do tempo configurável, a chamada tocará novamente para a pessoa que a estacionou. Se essa pessoa não atender, a chamada será transferida para um destino de fallback, como um operador, se assim estiver configurado. Você pode configurar o número de vezes que a chamada toca antes de ser transferida, entre uma a dez vezes. Se ninguém atender a chamada transferida, ela será desconectada. A órbita é liberada quando a chamada é recebida ou desconectada.
  
Quando você implanta o Estacionamento de Chamada, precisa reservar intervalos de números de extensão para estacionar as chamadas. Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído. Você configura a tabela de órbitas do estacionamento de chamada com os intervalos de números de extensões e especifica qual serviço de Aplicativo hospeda o aplicativo de Estacionamento de Chamada que lida com cada intervalo. Cada pool de front-ends tem uma tabela parque de chamadas no servidor back-end correspondente usado para gerenciar chamadas estacionadas no pool. A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino. Cada pool do Skype for Business Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita. As faixas órbitas devem ser globalmente exclusivas em toda a implantação do Skype for Business Server. 
  
Você também define outras configurações de Estacionamento de Chamada, como para onde as chamadas são redirecionadas quando atingem o tempo limite e se a pessoa ao telefone ouve música enquanto aguarda. Você também pode especificar o arquivo de música a ser reproduzido enquanto a chamada está em espera.
  
> [!NOTE]
> Os arquivos personalizados de música em espera para o parque de chamadas não fazem backup como parte do processo de recuperação de desastres do Skype for Business Server e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada. 
  
O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice. Ao implantar o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente. No entanto, antes de poder usar o parque de chamadas, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo de estacionamento de chamadas é instalado automaticamente quando você implanta o Enterprise Voice. Para habilitar o estacionamento de chamadas, configure a política de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos os servidores de front-end e servidores Standard Edition nos quais o estacionamento de chamadas é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores executando o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows. O tempo de execução do Windows Media Format ou do Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento reproduz para música em espera.
  
### <a name="port-requirements"></a>Requisitos de porta

O aplicativo parque de chamadas usa a **porta 5075** para solicitações de escuta SIP.
    
> [!NOTE]
> Esta porta é uma configuração padrão, que pode ser alterada usando o cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de estacionamento de chamadas só dá suporte a arquivos de áudio do Windows Media (. WMA) para música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar o Expression Encoder 4, consulte ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Use a ferramenta para converter o arquivo para o formato .wma. O formato recomendado para os arquivos de áudio da chamada com vídeo em espera é áudio de mídia 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.
  
> [!NOTE]
> O arquivo convertido é reproduzido no telefone apenas em 16 kHz, mesmo que tenha sido gravado em 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Chamadas e clientes suportados

Os seguintes clientes e tipos de chamadas são compatíveis com o parque de chamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes com suporte para Estacionamento de Chamadas

Chamadas de qualquer telefone IP, PBX, PSTN ou celular podem ser estacionadas.
  
> [!NOTE]
> Apenas chamadas de áudio podem ser estacionadas. Conferências e mensagens instantâneas não podem ser estacionadas. 
  
Os seguintes clientes podem usar o estacionamento de chamadas para estacionar chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Telefones celulares não podem usar o estacionamento de chamadas para fazer chamadas para estacionar. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes com suporte para Recuperação de Chamadas

Os intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído). Quando você configura órbitas como extensões virtuais, os celulares e telefones PSTN não podem recuperar as chamadas estacionadas.
  
Os usuários federados não podem recuperar chamadas estacionadas.
  
Os seguintes clientes podem recuperar chamadas estacionadas no parque da chamada:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Telefones de área comuns IP
    
- Telefones não IP que estão conectados à infraestrutura do Skype for Business Server, incluindo telefones de área comum e telefones PBX (Private Branch Exchange)
    
## <a name="call-park-capacity-planning"></a>Planejamento de capacidade do Estacionamento de Chamada

A tabela a seguir descreve o modelo de usuário do parque de chamadas que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de estacionamento de chamadas em ambos os pools. 
  
**Modelo de usuário do estacionamento de chamada**

|**Indicador**|**Por pool <br/> de front-end (com 8 servidores front end)**|**Por servidor padrão da edição**|
|:-----|:-----|:-----|
|Taxa de estacionamento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Recuperar a taxa de chamada estacionada  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Duração média do estacionamento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

