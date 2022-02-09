---
title: Planejar estacionamento de chamada no Skype for Business
ms.reviewer: ''
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
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planejando o estacionamento de chamadas Skype for Business Server Enterprise Voice, o que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas com suporte e clientes com suporte.
ms.openlocfilehash: a0102dea8a9511fae4031e41230c125b55d14844
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401765"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Planejar estacionamento de chamada no Skype for Business
 
Planejando o estacionamento de chamadas Skype for Business Server Enterprise Voice, o que permite colocar chamadas em espera e transferir chamadas para departamentos. Inclui planejamento de capacidade, chamadas com suporte e clientes com suporte.
  
O aplicativo Estacionamento de Chamada permite Enterprise Voice usuários para fazer o seguinte:
  
- Coloque uma chamada em espera e recupere a chamada do mesmo telefone ou de outro telefone.
    
- Colocar uma chamada em espera para transferi-la para um departamento ou área geral (por exemplo, para um departamento de vendas ou um depósito onde há um telefone de área comum).
    
- Coloque uma chamada em espera e mantenha o telefone de atendimento original livre para outras chamadas.
    
Quando um usuário estaciona uma chamada, Skype for Business Server transfere a chamada para um número temporário, chamado de órbita, onde a chamada é mantida até que seja recuperada ou ela se esvae. Skype for Business Server envia a órbita para o usuário que estacionou a chamada. Para recuperar a chamada estacionada, o usuário pode discar o número da órbita ou clicar no link de órbita ou no botão na janela Conversa. 
  
O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas (IM) ou um sistema de pajamento, para comunicar o número da órbita a outra pessoa. O usuário que estacionou a chamada pode deixar a janela Conversa aberta para receber notificação quando a chamada for recuperada.
  
Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site Skype for Business Server ou telefone PBX se o roteamento estiver configurado adequadamente. Se ninguém recuperar a chamada em um período configurável, a chamada tocará de volta para a pessoa que a estacionou. Se essa pessoa não responder ao toque de retorno, a chamada será transferida para um destino de fallback, como para um operador, se estiver configurado. Você pode configurar o número de vezes que a chamada toca antes de ser transferida de uma a dez vezes. Se ninguém atender a uma chamada transferida, a chamada será desconectada. A órbita é liberada quando a chamada é recuperada ou desconectada.
  
Ao implantar o Estacionamento de Chamadas, você precisa reservar intervalos de números de ramal para chamadas de estacionamento. Essas extensões precisam ser extensões virtuais: extensões que não têm usuário ou telefone atribuído a eles. Em seguida, configure a tabela de órbita do estacionamento de chamada com os intervalos de números de extensão e especifique qual serviço application hospeda o aplicativo Estacionamento de Chamada que lida com cada intervalo. Cada pool de Front-End tem uma tabela estacionamento de chamadas no Servidor Back-End correspondente que é usado para gerenciar chamadas estacionadas no pool. A lista de intervalos de órbitas é armazenada no Armazenamento de Gerenciamento Central e é usada para rotear órbitas para o pool de destino. Cada Skype for Business Server pool em que o aplicativo Estacionamento de Chamada é implantado e configurado pode ter um ou mais intervalos de órbita. Os intervalos de órbita devem ser globalmente exclusivos em toda Skype for Business Server implantação. 
  
Você também configura outras configurações de Estacionamento de Chamadas, como onde as chamadas são redirecionadas se o tempo de saída e se a pessoa no telefone ouvir música enquanto estacionada. Você também pode especificar o arquivo de música a ser reproduzir enquanto a chamada está em espera.
  
> [!NOTE]
> Arquivos personalizados de música em espera para Estacionamento de Chamada não são backups como parte do processo de recuperação de desastres do Skype for Business Server e serão perdidos se os arquivos carregados no pool são danificados, corrompidos ou apagados. Sempre mantenha uma cópia de backup separada dos arquivos personalizados de música em espera que você carregou para Estacionamento de Chamada. 
  
O aplicativo Estacionamento de Chamada é um componente Enterprise Voice. Quando você implanta Enterprise Voice, o aplicativo Estacionamento de Chamada é instalado e ativado automaticamente. Antes de poder usar o Estacionamento de Chamadas, no entanto, o Enterprise Voice administrador deve configurá-lo e habilita-lo para os usuários por meio da política de voz.
  
## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo Estacionamento de Chamada é instalado automaticamente quando você implanta Enterprise Voice. Você habilita o Estacionamento de Chamadas configurando a política de voz.
  
### <a name="software-requirements"></a>Requisitos de software

Todos os servidores front-end e servidores Edição Standard em que o Estacionamento de Chamada está implantado devem ter o tempo de execução do formato de mídia do Windows instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Tempo de Execução de Formato de Mídia é instalado como parte do Windows Desktop Experience. Windows Tempo de Execução de Formato de Mídia ou Microsoft Media Windows Foundation é necessário para arquivos de áudio de mídia (.wma) que o Estacionamento de Chamada reproduz para música em espera.
  
### <a name="port-requirements"></a>Requisitos de porta

O aplicativo Estacionamento de Chamada usa **a Porta 5075 para**  solicitações de escuta SIP.
    
> [!NOTE]
> Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de Gerenciamento do Lync Server.
  
### <a name="audio-file-requirements"></a>Requisitos de arquivo de áudio

O aplicativo Estacionamento de Chamada dá suporte Windows arquivos de Áudio de Mídia (.wma) para música em espera. É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera. Para baixar o Codificador de Expressão 4, consulte   ["Codificador de Expressão 4"](https://go.microsoft.com/fwlink/p/?linkId=202843). Use a ferramenta para converter o arquivo no formato .wma. O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.
  
> [!NOTE]
> O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz. 
  
## <a name="supported-clients-and-calls"></a>Clientes e chamadas com suporte

Os seguintes clientes e tipos de chamadas são suportados para Estacionamento de Chamadas
  
### <a name="clients-supported-for-parking-calls"></a>Clientes com suporte para chamadas de estacionamento

As chamadas de qualquer IP, PBX (private branch exchange), PSTN (rede telefônica pública comutado) ou telefone celular podem ser estacionadas.
  
> [!NOTE]
> Somente chamadas de áudio podem ser estacionadas. Mensagens instantâneas e conferências não podem ser estacionadas. 
  
Os seguintes clientes podem usar Call Park para estacionar chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Os telefones celulares não podem usar o Estacionamento de Chamadas para estacionar chamadas. 
  
### <a name="clients-supported-for-retrieving-calls"></a>Clientes com suporte para recuperação de chamadas

Intervalos de órbita são configurados como blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído). Quando você configura órbitas como extensões virtuais, telefones celulares e telefones PSTN não podem recuperar chamadas estacionadas.
  
Os usuários federados não podem recuperar chamadas estacionadas.
  
Os seguintes clientes podem recuperar chamadas estacionadas no Estacionamento de Chamadas:
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- Telefones de área comum IP
    
- Telefones não IP conectados à infraestrutura Skype for Business Server, incluindo telefones de área comum e telefones PBX (private branch exchange)
    
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
   

