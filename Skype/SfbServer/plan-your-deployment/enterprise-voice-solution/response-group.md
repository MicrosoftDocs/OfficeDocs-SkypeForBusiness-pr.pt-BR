---
title: Plano do aplicativo grupo de resposta no Skype for Business Server
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
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planejamento de grupos de resposta no Skype for Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: b1c8a2ab1a7dc42fd290df4bdc1ccf69b52db43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276465"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Plano do aplicativo grupo de resposta no Skype for Business Server

Planejamento de grupos de resposta no Skype for Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.

Se a sua organização tiver grupos de pessoas que atendem e gerenciem certos tipos de chamadas, como para atendimento ao cliente, um suporte técnico interno ou um suporte por telefone geral para um departamento, você pode implantar o aplicativo grupo de resposta para gerenciar esses tipos de chamadas. O aplicativo grupo de resposta roteia e enfileira chamadas recebidas para pessoas designadas, que são conhecidas como agentes. Você pode aumentar o uso de serviços de suporte telefônico e reduzir a sobrecarga de execução desses serviços usando grupos de resposta.

Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou nas respostas do chamador às perguntas de IVR (resposta de voz interativa). O aplicativo grupo de resposta usa métodos de roteamento de grupo de resposta padrão para direcionar a chamada para o próximo agente disponível. Os métodos de roteamento de chamada incluem serial, ocioso por mais tempo, paralelo, round robin, e roteamento de Atendedor (ou seja, todos os agentes são chamados ao mesmo tempo a cada chamada de entrada, independentemente de sua presença atual).

Se não houver agentes disponíveis, a chamada será mantida em uma fila até que um agente fique disponível. Enquanto está na fila, o chamador ouve música até um agente disponível aceitar a chamada. Se a fila estiver cheia ou se a chamada expirar enquanto estiver na fila, o chamador poderá ouvir uma mensagem e ser desconectado ou transferido para outro destino, como outro número de telefone ou a caixa postal. Quando um agente aceita a chamada, o chamador pode ou não ser capaz de ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta. Os agentes podem ser formais, o que significa que eles devem entrar no grupo antes de aceitar chamadas encaminhadas para o grupo, ou informais, o que significa que eles não precisam entrar no grupo para aceitar chamadas.

> [!NOTE]
> Somente os usuários no local podem ser agentes. Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.

> [!NOTE]
> O aplicativo grupo de resposta usa um serviço interno, chamado fazer correspondência, para enfileirar chamadas e localizar agentes disponíveis. Cada computador que executa o aplicativo do grupo de resposta executa o serviço fazer correspondência, mas apenas uma correspondência para fazer o serviço por pool está ativa de cada vez--os outros são passivos. Se a correspondência ativa que faz o serviço ficar indisponível durante uma interrupção não planejada, um dos serviços de correspondência passiva será ativado. O aplicativo grupo de resposta faz o melhor possível para garantir que o encaminhamento de chamadas e o enfileiramento continuem ininterruptos. No entanto, quando ocorre uma correspondência fazendo a transição do serviço, todas as chamadas que estão sendo transferidas no momento são perdidas. Por exemplo, se a transição for devida ao servidor de front-end, todas as chamadas atualmente manipuladas pela correspondência ativa que está fazendo o serviço nesse servidor front-end também serão perdidas.

## <a name="response-group-workflows"></a>Fluxos de trabalho de grupo de resposta

Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho especifica a fila a ser usada para manter a chamada e especifica o método de roteamento a ser usado para grupos de busca ou perguntas e respostas a serem usadas para grupos de resposta interativos. Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.

> [!NOTE]
> Você deve criar grupos de agente e filas antes de criar um fluxo de trabalho que os utiliza.

## <a name="management-of-response-groups"></a>Gerenciamento de grupos de resposta

No Skype for Business Server, duas funções de gerenciamento estão disponíveis para o gerenciamento de grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta. Os administradores de grupo de resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta. Os gerentes de grupo de resposta podem gerenciar apenas determinados aspectos e somente para os grupos de resposta que eles possuem. A função gerente pode ajudá-lo a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos para qualquer usuário habilitado para o Enterprise Voice. Observe que um usuário pode ser um gerente de grupo de resposta e um administrador de grupo de resposta.

Para acomodar a função gerente, o aplicativo de grupo de resposta usa um **tipo de fluxo de trabalho** gerenciado ou não gerenciado. A tabela a seguir descreve os grupos de resposta gerenciados e não gerenciados.

**Grupos de resposta gerenciados e não gerenciados**

|**Tipo de grupo de resposta**|**Descrição**|
|:-----|:-----|
|Não gerenciado  <br/> | Os grupos de resposta não gerenciados não têm gerentes atribuídos. Somente o administrador do grupo de resposta pode configurar esses grupos de resposta. <br/>  Vários grupos de resposta não gerenciados podem compartilhar uma fila ou um grupo de agente. <br/>  Ao migrar grupos de resposta de uma versão anterior para o Skype for Business Server, o tipo é definido como não gerenciado. <br/> |
|Gerenciado  <br/> | Os administradores de grupo de resposta podem configurar qualquer aspecto de grupos de resposta gerenciado. <br/>  Os gerentes de grupo de resposta não podem exibir ou modificar os grupos de resposta que não foram atribuídos explicitamente a eles. <br/>  Os gerentes de grupo de resposta podem configurar apenas algumas configurações para os grupos de resposta atribuídos explicitamente a eles. <br/>  Grupos de resposta gerenciada não podem compartilhar filas ou grupos de agente com qualquer outro grupo de resposta, gerenciado ou não gerenciado. <br/> |

A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem e não podem realizar para os grupos de resposta atribuídos a eles.

**Funcionalidades do Gerenciador de grupo de resposta**

|**Pode configurar:**|**Pode criar, excluir ou configurar:**|**Consegue**|
|:-----|:-----|:-----|
| Agentes <br/>  Mensagem de boas-vindas <br/>  Nome do grupo de resposta <br/>  Descrição <br/>  Número para exibição <br/>  Horário comercial <br/>  Música de espera <br/>  Status (ativo/inativo) <br/>  Fluxos de trabalho de grupo de busca ou de reação de voz interativa (IVR) <br/> | Grupos de agente <br/>  Filas <br/>  Conjuntos de feriados <br/> | Criar ou excluir qualquer tipo de fluxo de trabalho <br/>  Modifique as configurações do grupo de respostas principais, como: **URI SIP**, **número de telefone**ou **tipo de fluxo de trabalho**.  <br/> |

Os gerentes de grupo de resposta podem usar as seguintes ferramentas para gerenciar os grupos de resposta designados.

- Painel de Controle do Skype for Business Server

    > [!NOTE]
    > Os gerentes de grupo de resposta só podem gerenciar as configurações de grupo de resposta com essa ferramenta. Outras configurações do Skype for Business Server não estão disponíveis para gerentes.

- Ferramenta de Configuração de Grupo de Resposta

- Shell de Gerenciamento do Skype for Business Server

O grupo de resposta é dimensionado bem para ambientes de departamento ou de grupo de trabalho (para obter detalhes, consulte [planejamento de capacidade para o grupo de resposta](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) e pode ser implantado em instalações de telefonia totalmente novas. Ele é compatível com chamadas de implantação do Enterprise Voice e da rede da operadora local. Os agentes podem usar o Skype for Business, o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para fazer as chamadas serem encaminhadas para eles.

## <a name="deployment-and-requirements"></a>Implantação e requisitos

O aplicativo grupo de resposta é habilitado automaticamente quando você implanta o Enterprise Voice.

### <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

O aplicativo grupo de resposta tem os mesmos requisitos de hardware, requisitos do sistema operacional e pré-requisitos de software como servidores front-end.

Se você usa arquivos de áudio do Windows Media (. WMA) para músicas e anúncios em grupo de resposta, todos os servidores front-end ou servidores Standard Editions que executam o aplicativo do grupo de resposta devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2. Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.

O grupo de resposta usa **pacotes de idiomas** para dar suporte a conversão de texto em fala e reconhecimento de fala. Essas tecnologias de fala são usadas quando você configura mensagens, como a mensagem de boas-vindas e outros avisos e perguntas e respostas de reação interativas de voz (IVR). Por padrão, os 26 pacotes de idiomas com suporte são instalados quando você implanta o Skype for Business Server.

### <a name="port-requirements"></a>Requisitos de porta

O aplicativo grupo de resposta usa as seguintes portas:

- **Porta 5071** para solicitações de escuta SIP

- **Porta 8404** para comunicações entre servidores

    > [!NOTE]
    > Essa porta é usada para o serviço fazer correspondência e é necessária quando o aplicativo do grupo de resposta é implantado em um pool que tem mais de um servidor front-end.

   > [!NOTE]
   > Essas portas são configurações padrão que podem ser alteradas usando o cmdlet **set-CsApplicationServer** . Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Skype for Business Server.

### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O aplicativo de grupo de resposta suporta o formato de arquivo Wave (. wav) e o formato de áudio do Windows Media (. WMA) para perguntas sobre mensagens de grupo de resposta, música em espera ou reação de voz interativa (IVR).

O formato de arquivo de áudio do Windows Media requer que o tempo de execução do Windows Media Format seja instalado em servidores front-end que executam o Windows Server 2008 R2 e o Windows Server 2008. Para obter mais detalhes, consulte "requisitos de software", anteriormente nesta seção.

#### <a name="supported-wave-file-formats"></a>Formatos de arquivo wave compatíveis

Todos os arquivos de ondas devem atender aos seguintes requisitos:

- arquivo de 8 bits ou 16 bits

- Formato de modulação de código de pulso linear (LPCM), A-lei ou MU-Law

- Mono ou estéreo

- 4 MB ou menos

Para obter o melhor desempenho de arquivos Wave, recomenda-se um arquivo wave de 16 kHz, mono e 16 bits.

#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de arquivo de áudio do Windows Media com suporte

Se você usar um arquivo de áudio do Windows Media, considere o uso de taxas de bits baixas e verifique se o desempenho do sistema está em carga.

Você pode usar o codificador do Microsoft Expression 4 para converter um arquivo para o formato de áudio do Windows Media. Para baixar o Expression Encoder 4, [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)consulte.

### <a name="response-group-configuration-tool-requirements"></a>Requisitos da ferramenta de configuração de grupo de resposta

A ferramenta de configuração de grupo de resposta aceita as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

> [!NOTE]
> Há suporte para as versões de 32 bits ou 64 bits dos sistemas operacionais. Só há suporte para as versões de 32 bits do Internet Explorer.

**Navegadores da Web e sistemas operacionais com suporte**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console do agente do grupo de resposta

O console do agente tem suporte para as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

> [!NOTE]
> Há suporte para as versões de 32 bits ou 64 bits dos sistemas operacionais. Só há suporte para as versões de 32 bits do Internet Explorer.

**Navegadores da Web e sistemas operacionais com suporte**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10,0  <br/> Chrome 18,0  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10,0  <br/> Chrome 18,0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Suporte ao cliente

O aplicativo de grupo de resposta é compatível com os seguintes clientes:

- Cliente de desktop do Skype for Business

- Cliente de desktop do Lync 2013

- Cliente de desktop do Lync 2010

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Não há suporte para o aplicativo grupo de resposta em clientes móveis do Lync.

O cliente específico que você pode usar depende do tipo de usuário do grupo de resposta que você está:

- **** Os chamadores podem chamar um grupo de resposta usando qualquer um dos clientes listados anteriormente e usando um telefone padrão na rede telefônica pública comutada (PSTN).

- **Agentes** informais (os agentes que não entram e saem dos seus grupos para aceitar chamadas) podem aceitar chamadas usando o atendente, o Lync ou o Lync Phone Edition. Agentes informais são automaticamente conectados aos seus grupos quando entram no Skype for Business Server usando um desses clientes.

- **Agentes formais** (os agentes que devem entrar e sair de seus grupos para aceitar chamadas) podem aceitar chamadas usando o Skype for Business e acessando o console do agente a partir do item de menu ou usando o atendente e acessando o console do agente diretamente do Internet Explorer.

## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para requisitos de planejamento de capacidade.

> [!NOTE]
> Os números na tabela a seguir pressupõem que você use arquivos Wave de 16 bits (. wav) de 16 bits para todos os arquivos de áudio do grupo de resposta. Se você usar outros formatos de arquivo, como o áudio do Windows Media (. WMA), os números podem variar.

> [!IMPORTANT]
> Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para todos os grupos de resposta em ambos os pools.

**Modelo de usuário do grupo de resposta**

|**Indicador**|**Por pool <br/> de edição para empresas (com 8 servidores front end)**|**Por servidor padrão da edição**|
|:-----|:-----|:-----|
|Chamadas recebidas por segundo  <br/> |16  <br/> |2  <br/> |
|Chamadas simultâneas conectadas ao IVR ou MoH  <br/> |480  <br/> |60  <br/> |
|Sessões anônimas simultâneas (sem mensagens instantâneas)  <br/> |224  <br/> |28  <br/> |
|Sessões anônimas simultâneas (com mensagens instantâneas)  <br/> |64  <br/> |08  <br/> |
|Agentes ativos (formais e informais)  <br/> |2400  <br/> |2400  <br/> |
|Número de grupos de busca  <br/> |800  <br/> |800  <br/> |
|Número de grupos IVR (usar reconhecimento de fala)  <br/> |400  <br/> |400  <br/> |


