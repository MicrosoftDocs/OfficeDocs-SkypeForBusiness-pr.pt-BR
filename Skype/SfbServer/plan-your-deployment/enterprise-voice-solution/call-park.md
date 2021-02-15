---
title: Planejar o Estacionamento de Chamadas no Skype for Business
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejamento para estacionamento de chamada no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas com suporte e clientes suportados.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825921"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planejar o Estacionamento de Chamadas no Skype for Business
 
Planejamento para estacionamento de chamada no Skype for Business Server Enterprise Voice, que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas com suporte e clientes suportados.
  
O aplicativo Estacionamento de Chamada permite que os usuários do Enterprise Voice faça o seguinte:
  
- Coloque uma chamada em espera e recupere a chamada do mesmo telefone ou de outro telefone.
    
- Colocar uma chamada em espera para transferi-la para um departamento ou área geral (por exemplo, para um departamento de vendas ou um depósito onde há um telefone de área comum).
    
- Coloque uma chamada em espera e mantenha o telefone de atendimento original livre para outras chamadas.
    
Quando um usuário estaciona uma chamada, o Skype for Business Server transfere a chamada para um número temporário, chamado órbita, onde a chamada é mantida até que seja recuperada ou o tempo se esvae. O Skype for Business Server envia a órbita para o usuário que estacionou a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número da órbita ou clicar no link de órbita ou no botão na janela conversa. 
  
O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas (IM) ou um sistema de paging, para comunicar o número da órbita a outra pessoa. O usuário que estacionou a chamada pode deixar a janela conversa aberta para receber notificação quando a chamada é recuperada.
  
Como os intervalos de órbitas são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Skype for Business Server ou telefone PBX se o roteamento estiver configurado adequadamente. Se ninguém recuperar a chamada dentro de um período de tempo configurável, a chamada tocará de volta para a pessoa que a estacionou. Se essa pessoa não atender o retorno de toque, a chamada será transferida para um destino de fallback, como para um operador, se estiver configurado. Você pode configurar o número de vezes que a chamada toca antes de ser transferida de uma a dez vezes. Se ninguém atender a uma chamada transferida, ela será desconectada. A órbita é liberada quando a chamada é recuperada ou desconectada.
  
Ao implantar o Estacionamento de Chamada, você precisa reservar intervalos de ramais para estacionar chamadas. Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído a elas. Em seguida, configure a tabela de órbita de estacionamento de chamada com os intervalos de números de ramal e especifique qual serviço de aplicativo hospeda o aplicativo Estacionamento de Chamada que lida com cada intervalo. Cada pool de Front-End tem uma tabela estacionamento de chamadas no Servidor back-end correspondente que é usado para gerenciar chamadas estacionadas no pool. A lista de intervalos de órbitas é armazenada no armazenamento de Gerenciamento Central e é usada para rotear órbitas para o pool de destino. Cada pool do Skype for Business Server onde o aplicativo Estacionamento de Chamada é implantado e configurado pode ter um ou mais intervalos de órbitas. Os intervalos de órbita devem ser globalmente exclusivos na implantação do Skype for Business Server. 
  
Você também define outras configurações de Estacionamento de Chamadas, como para onde as chamadas são redirecionadas se o tempo passar e se a pessoa no telefone ouve música enquanto está estacionada. Você também pode especificar o arquivo de música a ser tocar enquanto a chamada estiver em espera.
  
> [!NOTE]
> Arquivos de música de espera personalizados para Estacionamento de Chamada não são armazenados como parte do processo de recuperação de desastres do Skype for Business Server e serão perdidos se os arquivos carregados no pool estão danificados, corrompidos ou apagados. Sempre mantenha uma cópia de backup separada dos arquivos de música de espera personalizados que você carregou para o Estacionamento de Chamada. 
  
O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice. Quando você implanta o Enterprise Voice, o aplicativo Estacionamento de Chamada é instalado e ativado automaticamente. Antes de poder usar o Estacionamento de Chamada, no entanto, o administrador do Enterprise Voice deve configurá-lo e habilita-lo para os usuários por meio da política de voz.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo Estacionamento de Chamada é instalado automaticamente quando você implanta o Enterprise Voice. Você habilita o Estacionamento de Chamada configurando a política de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos os servidores Front End e Standard Edition onde o Estacionamento de Chamada é implantado devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o Windows Media Format Runtime é instalado como parte da Experiência Desktop do Windows. O Tempo de Execução do Windows Media Format ou o Microsoft Media Foundation são necessários para arquivos .wma (Windows Media Audio) que o Estacionamento de Chamada reproduz para música em espera.
  
### <a name="port-requirements"></a>Requisitos de porta

O aplicativo Estacionamento de Chamada usa **a Porta 5075 para**  solicitações de escuta SIP.
    
> [!NOTE]
> Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de Gerenciamento do Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de arquivo de áudio

O aplicativo Estacionamento de Chamada dá suporte apenas a arquivos .wma (Windows Media Audio) para música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar o Expression Encoder 4, consulte   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Use a ferramenta para converter o arquivo no formato .wma. O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Clientes e chamadas com suporte

Os seguintes clientes e tipos de chamadas são suportados para Estacionamento de Chamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes com suporte para estacionamento de chamadas

Chamadas de qualquer IP, PBX (central privada de comução), PSTN (rede telefônica pública comutado) ou telefone celular podem ser estacionadas.
  
> [!NOTE]
> Somente chamadas de áudio podem ser estacionadas. As mensagens instantâneas e conferências não podem ser estacionadas. 
  
Os clientes a seguir podem usar o Estacionamento de Chamada para estacionar chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Os telefones celulares não podem usar o Estacionamento de Chamadas para estacionar chamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes com suporte para recuperação de chamadas

Os intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído). Quando você configura órbitas como extensões virtuais, telefones celulares e telefones PSTN não podem recuperar chamadas estacionadas.
  
Os usuários federados não podem recuperar chamadas estacionadas.
  
Os clientes a seguir podem recuperar chamadas estacionadas no Estacionamento de Chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Telefones de área comum IP
    
- Telefones não IP que estão conectados à infraestrutura do Skype for Business Server, incluindo telefones de área comum e telefones PBX (central privada de comutamento)
    
## <a name="call-park-capacity-planning"></a>Planejamento de capacidade do Estacionamento de Chamada

A tabela a seguir descreve o modelo de usuário estacionamento de chamada que você pode usar como base para requisitos de planejamento de capacidade.
  
> [!IMPORTANT]
> Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de Estacionamento de Chamada em ambos os pools. 
  
**Modelo de usuário do estacionamento de chamada Park**

|**Indicador**|**Por pool de front-end  <br/>  (com 8 servidores front-end)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Taxa de estacionamento  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Recuperar a taxa de chamada estacionada  <br/> |8 por minuto  <br/> |1 por minuto  <br/> |
|Duração média do estacionamento  <br/> |60 segundos  <br/> |60 segundos  <br/> |
   

