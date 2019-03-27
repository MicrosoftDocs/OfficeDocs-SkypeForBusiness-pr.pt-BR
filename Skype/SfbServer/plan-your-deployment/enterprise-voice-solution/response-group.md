---
title: Plano para o aplicativo de grupo de resposta no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Planejamento de grupos de resposta no Skype para Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.
ms.openlocfilehash: 68a693715739d58488e134934416790641dd091e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894399"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Plano para o aplicativo de grupo de resposta no Skype para Business Server

Planejamento de grupos de resposta no Skype para Business Server Enterprise Voice, que permite configurar o roteamento de chamadas para grupos de usuários. Inclui requisitos de arquivo de áudio.

Se sua organização tiver grupos de pessoas que atender e gerenciar determinados tipos de chamadas, tais como para atendimento ao cliente, um técnico interno ou suporte por telefone gerais para um departamento, você pode implantar o aplicativo de grupo de resposta para gerenciar esses tipos de chamadas. Aplicativo roteia e enfileira chamadas de entrada para o grupo de resposta designado pessoas, que são conhecidas como agentes. Você pode aumentar o uso de serviços de suporte telefônico e reduzir a sobrecarga de execução desses serviços usando grupos de resposta.

Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou nas respostas do chamador às perguntas de IVR (resposta de voz interativa). Aplicativo grupo de resposta usa os métodos de roteamento de grupo de resposta padrão para rotear a chamada para o próximo operador disponível. Os métodos de roteamento de chamada incluem serial, ocioso por mais tempo, paralelo, round robin, e roteamento de Atendedor (ou seja, todos os agentes são chamados ao mesmo tempo a cada chamada de entrada, independentemente de sua presença atual).

Se não houver agentes disponíveis, a chamada será mantida em uma fila até que um agente fique disponível. Enquanto está na fila, o chamador ouve música até um agente disponível aceitar a chamada. Se a fila estiver cheia ou se a chamada expirar enquanto estiver na fila, o chamador poderá ouvir uma mensagem e ser desconectado ou transferido para outro destino, como outro número de telefone ou a caixa postal. Quando um agente aceita a chamada, o chamador pode ou não ser capaz de ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta. Os agentes podem ser formais, o que significa que eles devem entrar no grupo antes de aceitar chamadas encaminhadas para o grupo, ou informais, o que significa que eles não precisam entrar no grupo para aceitar chamadas.

> [!NOTE]
> Somente os usuários no local podem ser agentes. Se um operador for movido de local para online, chamadas de grupo de resposta não serão roteadas para esse agente.

> [!NOTE]
> Aplicativo grupo de resposta usa um serviço interno, chamado de correspondência, para enfileirar chamadas e encontrar agentes disponíveis. Cada computador que executa o aplicativo grupo de resposta executa o serviço de correspondência, mas somente um serviço de correspondência por pool está ativo de cada vez – os outros estão passivos. Se o serviço de correspondência ativo ficar indisponível durante uma interrupção não planejada, um dos serviços de correspondência passivos ficará ativo. Esforça do aplicativo grupo de resposta para certificar-se de que o roteamento de chamada e enfileiramento continue sem interrupção. No entanto, quando uma transição de serviço de correspondência ocorre, todas as chamadas que estão na transferência no momento em que são perdidas. Por exemplo, se a transição é devido ao servidor Front-End diminuindo, todas as chamadas atualmente sendo manipuladas pelo serviço de correspondência ativo em que servidor Front-End também são perdidas.

## <a name="response-group-workflows"></a>Fluxos de trabalho de grupo de resposta

Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho Especifica a fila a ser usada para manter a chamada e especifica o método de roteamento a ser usado para grupos de busca ou as perguntas e respostas a ser usado para grupos de resposta interativa. Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.

> [!NOTE]
> Você deve criar grupos de agente e filas antes de criar um fluxo de trabalho que os utiliza.

## <a name="management-of-response-groups"></a>Gerenciamento de grupos de resposta

No Skype para Business Server, duas funções de gerenciamento estão disponíveis para o gerenciamento de grupos de resposta: gerente do grupo de resposta e o administrador do grupo de resposta. Os administradores do grupo de resposta podem gerenciar todos os aspectos de qualquer grupo de resposta. Gerentes de grupo de resposta podem gerenciar apenas alguns aspectos e somente para grupos de resposta que são proprietários. A função de gerente pode ajudar a reduzir os custos de administração, porque você pode delegar responsabilidades limitadas para grupos de resposta específicos a qualquer usuário que esteja habilitado para o Enterprise Voice. Observe que um usuário pode ser tanto um gerente de grupo de resposta como um administrador de grupo de resposta.

Para acomodar a função de gerente, o aplicativo grupo de resposta usa um **Tipo de fluxo de trabalho** do gerenciado ou não gerenciado. A tabela a seguir descreve os grupos de respostas gerenciado e não gerenciado.

**Grupos de respostas gerenciados e**

|**Tipo de grupo de resposta**|**Descrição**|
|:-----|:-----|
|Não gerenciado  <br/> | Os grupos de respostas não gerenciados não têm nenhuma os gerentes atribuídos. Somente o administrador do grupo de resposta pode configurar esses grupos de resposta. <br/>  Vários grupos de respostas não gerenciados podem compartilhar um fila ou grupo de agentes. <br/>  Quando você migra grupos de resposta de uma versão anterior para Skype para Business Server, o tipo é definido como não gerenciado. <br/> |
|Gerenciados  <br/> | Administradores de grupo de resposta podem configurar qualquer aspecto de grupos de respostas gerenciados. <br/>  Gerentes de grupo de resposta não conseguem exibir ou modificar os grupos de resposta que não sejam explicitamente atribuídos a eles. <br/>  Gerentes de grupo de resposta podem definir apenas algumas configurações dos grupos de respostas explicitamente atribuídos a eles. <br/>  Grupos de respostas gerenciados não podem compartilhas filas nem grupos de operadores com qualquer outro grupo de resposta, gerenciado ou não. <br/> |

A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem ou não executar para os grupos de resposta atribuídos a eles.

**Recursos do gerente de grupo de resposta**

|**Pode configurar:**|**Pode criar, excluir ou configurar:**|**Não é possível:**|
|:-----|:-----|:-----|
| Agentes <br/>  Mensagem de boas-vindas <br/>  Nome do grupo de resposta <br/>  Descrição <br/>  Número para exibição <br/>  Horário comercial <br/>  Música de espera <br/>  Status (ativo/inativo) <br/>  Fluxos de trabalho de grupo de busca ou fluxos de trabalho IVR (resposta) de voz interativa <br/> | Grupos de operadores <br/>  Filas <br/>  Conjuntos de feriados <br/> | Criar ou excluir qualquer tipo de fluxo de trabalho <br/>  Modificar configurações do grupo de resposta de núcleo, como: **URI do SIP**, **Número de telefone**ou **Tipo de fluxo de trabalho**.  <br/> |

Gerentes de grupo de resposta podem usar as seguintes ferramentas para gerenciar seus grupos de respostas designados.

- Painel de Controle do Skype for Business Server

    > [!NOTE]
    > Gerentes de grupo de resposta só podem gerenciar as configurações de grupo de resposta com esta ferramenta. Outro Skype pelas configurações do servidor de negócios não estão disponíveis para gerentes.

- Ferramenta de Configuração de Grupo de Resposta

- Shell de Gerenciamento do Skype for Business Server

Ambientes de grupo de trabalho ou escalas de grupo de resposta, bem como para departamental (para obter detalhes, consulte [Planejamento de capacidade para o grupo de resposta](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) e podem ser implantados em instalações telefônicas totalmente novas. Suporte a chamadas de entrada da implantação do Enterprise Voice e da rede local da operadora. Os operadores podem usar Skype para negócios, Lync 2013, Lync 2010, Lync 2010 Attendant ou o Lync Phone Edition para receber as chamadas roteadas para eles.

## <a name="deployment-and-requirements"></a>Implantação e requisitos

Aplicativo grupo de resposta é ativado automaticamente quando você implanta o Enterprise Voice.

### <a name="hardware-and-software-requirements"></a>Requisitos de hardware e software

Aplicativo grupo de resposta tem os mesmos requisitos de hardware, requisitos de sistema operacional e os pré-requisitos de software, como servidores Front-End.

Se você usar os arquivos do Windows Media Audio (. wma) para anúncios e música de grupo de resposta, todos os servidores Front-End ou edições Standard servidores que executam o aplicativo grupo de resposta devem ter o Windows Media Format Runtime instalado para servidores que executam o Windows Server 2008 R2 ou Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2. Para Windows Server 2008 R2, Windows Media Format Runtime é instalado como parte da experiência de área de trabalho do Windows.

Grupo de resposta usa **pacotes de idiomas** para dar suporte ao texto em fala e reconhecimento de fala. Essas tecnologias de fala são usadas ao configurar mensagens, como a mensagem de boas-vindas e outras prompts e voz interativa (IVR) perguntas e respostas resposta. Por padrão, o 26 suportado language packs estão instalados quando você implanta o Skype para Business Server.

### <a name="port-requirements"></a>Requisitos de porta

O aplicativo grupo de resposta usa as seguintes portas:

- **Porta 5071** para solicitações de escuta SIP

- **Porta 8404** para comunicações entre servidores

    > [!NOTE]
    > Essa porta é usada para o serviço de correspondência e é necessária quando o aplicativo grupo de resposta é implantado em um pool que tenha mais de um servidor Front-End.

   > [!NOTE]
   > Essas portas são as configurações padrão que você pode alterar usando o cmdlet **Set-CsApplicationServer** . Para obter detalhes sobre esse cmdlet, consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.

### <a name="audio-file-requirements"></a>Requisitos do arquivo de áudio

O formato de arquivo wave (. wav) do grupo de resposta aplicativo suporta e o arquivo de áudio (. wma) do Windows Media format para mensagens do grupo de resposta, música de espera ou perguntas de IVR (resposta) interativa de voz.

O formato de arquivo de áudio Windows Media exige que o Windows Media Format Runtime é instalado nos servidores Front-End executando o Windows Server 2008 R2 e Windows Server 2008. Para obter mais detalhes, consulte "Requisitos de Software", anteriormente nesta seção.

#### <a name="supported-wave-file-formats"></a>Formatos de arquivo Wave suportados

Todos os arquivos wave devem atender aos seguintes requisitos:

- arquivo 8 bits ou 16 bits

- Modulação de código de pulso linear (LPCM), A-Law ou mu-Law formato

- Mono ou estéreo

- 4MB ou menos

Para obter o melhor desempenho de arquivos wave, um 16 kHz, recomenda-se o arquivo de Wave mono, 16 bits.

#### <a name="supported-windows-media-audio-file-formats"></a>Formatos de arquivo de áudio com suporte do Windows Media

Se você usar um arquivo de áudio Windows Media, considere o uso de taxas de bits baixa e verifique se o desempenho do sistema sob carga.

Você pode usar o Microsoft Expression codificador 4 para converter um arquivo para o formato do Windows Media Audio. Para baixar a expressão codificador 4, consulte [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).

### <a name="response-group-configuration-tool-requirements"></a>Requisitos de ferramenta de configuração de grupo de resposta

Ferramenta de configuração de grupo de resposta suporta as combinações de sistemas operacionais e navegadores da web descritos na tabela a seguir.

> [!NOTE]
> versões de 32 bits ou 64 bits dos sistemas operacionais são suportadas. Somente versões de 32 bits do Internet Explorer são suportadas.

**Sistemas operacionais e navegadores da Web**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console de agente do grupo de resposta

O console de agente suporta as combinações de sistemas operacionais e navegadores da web descritos na tabela a seguir.

> [!NOTE]
> versões de 32 bits ou 64 bits dos sistemas operacionais são suportadas. Somente versões de 32 bits do Internet Explorer são suportadas.

**Sistemas operacionais e navegadores da Web**

|**Sistema operacional**|**Navegador da Web**|
|:-----|:-----|
|Windows Vista com Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows 7  <br/> Windows 7 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 com Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 com Service Pack 1  <br/> |Internet Explorer 8 (modo nativo)  <br/> Internet Explorer 9 (modo nativo)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Suporte ao cliente

Aplicativo grupo de resposta suporta os seguintes clientes:

- Skype para o cliente de desktop de negócios

- Cliente de desktop do Lync 2013

- Cliente de desktop do Lync 2010

- Lync 2010 Attendant

- Atendedor do Office Communications Server 2007 R2

- Lync Phone Edition

> [!NOTE]
> Não há suporte para o aplicativo grupo de resposta em clientes móveis do Lync.

O cliente específico que você pode usar depende do tipo de grupo de resposta de usuário que você está:

- **Os chamadores** podem chamar um grupo de resposta usando quaisquer clientes listados anteriormente e usando um telefone padrão através da rede telefônica pública comutada (PSTN).

- **Operadores informais** (os operadores que não precisam entrar e sair de seus grupos para aceitar chamadas) podem aceitar chamadas usando o Lync Phone Edition, Lync ou Atendedor. Os operadores informais entrarão automaticamente em seus grupos quando entrarem no Skype para Business Server usando um destes clientes.

- **Operadores formais** (os operadores que devem entrar e sair de seus grupos para aceitar chamadas) podem aceitar chamadas usando o Skype para negócios e acessar o console de agente do item de menu ou usando o Attendant e acessar o console de agente diretamente no Internet Explorer.

## <a name="capacity-planning"></a>Planejamento de capacidade

A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para requisitos de planejamento de capacidade.

> [!NOTE]
> Os números na tabela a seguir pressupõem que você usa 16 kHz, mono, 16 bits Wave (. wav) arquivos para todos os arquivos de áudio de grupo de resposta. Se você usar outros formatos de arquivo, como o Windows Media Audio (. wma), os números podem variar.

> [!IMPORTANT]
> Tenha em mente que para o planejamento de capacidade de recuperação de desastres, cada pool de um pool pareado deve ser capaz de lidar com cargas de trabalho de todos os grupos de resposta em ambos os pools.

**Modelo de usuário do grupo de resposta**

|**Indicador**|**Por pool Enterprise Edition <br/> (com 8 servidores Front-End)**|**Por servidor Standard Edition**|
|:-----|:-----|:-----|
|Chamadas recebidas por segundo  <br/> |16  <br/> |2  <br/> |
|Chamadas concorrentes conectadas ao IVR ou MoH  <br/> |480  <br/> |60  <br/> |
|Sessões anônimas concorrentes (sem IM)  <br/> |224  <br/> |28  <br/> |
|Sessões anônimas concorrentes (com IM)  <br/> |64  <br/> |8  <br/> |
|Operadores ativos (formais e informais)  <br/> |2400  <br/> |2400  <br/> |
|Número de grupos de busca  <br/> |800  <br/> |800  <br/> |
|Número de grupos IVR (usa reconhecimento de fala)  <br/> |400  <br/> |400  <br/> |


