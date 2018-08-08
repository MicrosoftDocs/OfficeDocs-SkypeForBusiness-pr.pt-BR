---
title: Planejar o estacionamento de chamada no Skype for Business
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejamento de estacionamento de chamada no Skype para Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas e clientes compatíveis.
ms.openlocfilehash: a675100f8b40e1ab293c0240ea0acbe3beb7fa27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988547"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planejar o estacionamento de chamada no Skype for Business
 
Planejamento de estacionamento de chamada no Skype para Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas e clientes compatíveis.
  
O aplicativo de estacionamento de chamadas permite que os usuários do Enterprise Voice fazer o seguinte:
  
- Colocar uma chamada em espera e recuperá-la no mesmo telefone ou em outro.
    
- Colocar uma chamada em espera para transferi-la para um departamento ou área geral, por exemplo, um departamento de vendas ou um depósito onde há um telefone de área comum.
    
- Colocar uma chamada em espera e manter o telefone original livre para outras chamadas.
    
Quando um parques usuário uma chamada, Skype para Business Server transfere a chamada para um número temporário, chamado uma órbita, onde a chamada é mantida até que ele é recuperado ou ele expire. Skype para Business Server envia a órbita ao usuário que a colocou a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no link de órbita ou na janela de Conversação. 
  
O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas ou um sistema de paginação, para comunicar o número de órbita para outra pessoa. O usuário que estacionou a chamada pode deixar a janela de Conversação aberta para receber notificações quando a chamada for recuperada.
  
Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer Skype para site de Business Server ou o telefone PBX, se o roteamento está configurado de forma adequada. Se ninguém recuperar a chamada dentro do tempo configurável, a chamada tocará novamente para a pessoa que a estacionou. Se essa pessoa não atender, a chamada será transferida para um destino de fallback, como um operador, se assim estiver configurado. Você pode configurar o número de vezes que a chamada toca antes de ser transferida, entre uma a dez vezes. Se ninguém atender a chamada transferida, ela será desconectada. A órbita é liberada quando a chamada é recebida ou desconectada.
  
Quando você implanta o Estacionamento de Chamada, precisa reservar intervalos de números de extensão para estacionar as chamadas. Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído. Você configura a tabela de órbitas do estacionamento de chamada com os intervalos de números de extensões e especifica qual serviço de Aplicativo hospeda o aplicativo de Estacionamento de Chamada que lida com cada intervalo. Cada pool de Front-End tem uma tabela de estacionamento de chamada no correspondente servidor Back-End que é usado para gerenciar as chamadas estacionadas no pool. A lista de intervalos de órbita é armazenada no gerenciamento Central armazenar e é usado para rotear Órbitas para o pool de destino. Cada Skype para pool de servidores de negócios onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita. Intervalos de órbita devem ser exclusivos entre o Skype para implantação de servidor de negócios. 
  
Você também define outras configurações de Estacionamento de Chamada, como para onde as chamadas são redirecionadas quando atingem o tempo limite e se a pessoa ao telefone ouve música enquanto aguarda. Você também pode especificar o arquivo de música a ser reproduzido enquanto a chamada está em espera.
  
> [!NOTE]
> Arquivos de música de espera personalizados para estacionamento de chamada não backup como parte do Skype no processo de recuperação de desastres Business Server e serão perdidos se os arquivos carregados para o pool estiver danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada. 
  
O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice. Quando você implanta o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente. Antes de poder usar estacionamento de chamada, no entanto, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para usuários através da diretiva de voz.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo de estacionamento de chamada é instalado automaticamente quando você implanta o Enterprise Voice. Habilitar o estacionamento de chamada, configurando a política de voz.
  
### <a name="software-requirements"></a>Requisitos de software 

Todos os servidores Front-End e servidores Standard Edition onde o estacionamento de chamadas está implantado devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime é instalado como parte da experiência de área de trabalho do Windows. Windows Media Format Runtime ou Microsoft Media Foundation é obrigatório para arquivos de Windows Media Audio (. wma) que reproduz de estacionamento de chamadas para a música em espera.
  
### <a name="port-requirements"></a>Requisitos de porta

O aplicativo de estacionamento de chamada usa a **porta 5075** para solicitações de escuta SIP.
    
> [!NOTE]
> Essa porta é uma configuração padrão que você pode alterar usando o cmdlet **Set-CsApplicationServer** . Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O estacionamento de chamada aplicativo suporta apenas os arquivos de Windows Media Audio (. wma) para a música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar a expressão codificador 4, consulte ["Expressão codificador 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Use a ferramenta para converter o arquivo para o formato .wma. O formato recomendado para arquivos de música de espera do estacionamento de chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> O arquivo convertido é reproduzido no telefone apenas em 16 kHz, mesmo que tenha sido gravado em 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Chamadas e clientes suportados

Os clientes e os tipos de chamadas a seguir são suportados para estacionamento de chamada
  
### <a name="clients-supported-for-parking-calls"></a>Clientes com suporte para Estacionamento de Chamadas

Chamadas de qualquer telefone IP, PBX, PSTN ou celular podem ser estacionadas.
  
> [!NOTE]
> Apenas chamadas de áudio podem ser estacionadas. Conferências e mensagens instantâneas não podem ser estacionadas. 
  
Os seguintes clientes podem usar o estacionamento de chamada para estacionar chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Celulares não podem usar o estacionamento de chamada para estacionar chamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes com suporte para Recuperação de Chamadas

Os intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído). Quando você configura órbitas como extensões virtuais, os celulares e telefones PSTN não podem recuperar as chamadas estacionadas.
  
Os usuários federados não podem recuperar chamadas estacionadas.
  
Os seguintes clientes podem recuperar chamadas estacionadas no estacionamento de chamada:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Telefones de área comuns IP
    
- Telefones que não são IP que estão conectados a Skype a infra-estrutura de servidor de negócios, incluindo telefones de área comum e telefones do privada de comutação telefônica (PBX)
    
## <a name="call-park-capacity-planning"></a>Planejamento de capacidade do Estacionamento de Chamada

A tabela a seguir descreve o modelo de usuário do estacionamento de chamadas que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> Tenha em mente que, para o planejamento de capacidade de recuperação de desastres, cada pool de um pool pareado deve ser capaz de manipular cargas de trabalho para serviços de estacionamento de chamada em ambos os pools. 
  
**Modelo de usuário do estacionamento de chamada**

|**Métrica**|**Por pool de Front-End <br/> (com 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Taxa de estacionamento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Recuperar a taxa de chamada estacionada  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Duração média do estacionamento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

